                                      1 ;--------------------------------------------------------
                                      2 ; File Created by SDCC : free open source ISO C Compiler 
                                      3 ; Version 4.4.0 #14620 (Linux)
                                      4 ;--------------------------------------------------------
                                      5 	.module main
                                      6 	.optsdcc -mstm8
                                      7 	
                                      8 ;--------------------------------------------------------
                                      9 ; Public variables in this module
                                     10 ;--------------------------------------------------------
                                     11 	.globl _main
                                     12 	.globl _setup
                                     13 	.globl _max7219_init
                                     14 	.globl _TIM2_init
                                     15 	.globl _max7219_send
                                     16 	.globl _TIM2_ClearFlag
                                     17 	.globl _TIM2_ITConfig
                                     18 	.globl _TIM2_Cmd
                                     19 	.globl _TIM2_TimeBaseInit
                                     20 	.globl _GPIO_WriteLow
                                     21 	.globl _GPIO_WriteHigh
                                     22 	.globl _GPIO_Init
                                     23 	.globl _CLK_HSIPrescalerConfig
                                     24 	.globl _CLK_PeripheralClockConfig
                                     25 	.globl _svujcas
                                     26 ;--------------------------------------------------------
                                     27 ; ram data
                                     28 ;--------------------------------------------------------
                                     29 	.area DATA
                                     30 ;--------------------------------------------------------
                                     31 ; ram data
                                     32 ;--------------------------------------------------------
                                     33 	.area INITIALIZED
      000001                         34 _svujcas::
      000001                         35 	.ds 4
                                     36 ;--------------------------------------------------------
                                     37 ; Stack segment in internal ram
                                     38 ;--------------------------------------------------------
                                     39 	.area SSEG
      0086DE                         40 __start__stack:
      0086DE                         41 	.ds	1
                                     42 
                                     43 ;--------------------------------------------------------
                                     44 ; absolute external ram data
                                     45 ;--------------------------------------------------------
                                     46 	.area DABS (ABS)
                                     47 
                                     48 ; default segment ordering for linker
                                     49 	.area HOME
                                     50 	.area GSINIT
                                     51 	.area GSFINAL
                                     52 	.area CONST
                                     53 	.area INITIALIZER
                                     54 	.area CODE
                                     55 
                                     56 ;--------------------------------------------------------
                                     57 ; interrupt vector
                                     58 ;--------------------------------------------------------
                                     59 	.area HOME
      008000                         60 __interrupt_vect:
      008000 82 00 80 6F             61 	int s_GSINIT ; reset
      008004 82 00 83 20             62 	int _TRAP_IRQHandler ; trap
      008008 82 00 83 21             63 	int _TLI_IRQHandler ; int0
      00800C 82 00 83 22             64 	int _AWU_IRQHandler ; int1
      008010 82 00 83 23             65 	int _CLK_IRQHandler ; int2
      008014 82 00 83 24             66 	int _EXTI_PORTA_IRQHandler ; int3
      008018 82 00 83 25             67 	int _EXTI_PORTB_IRQHandler ; int4
      00801C 82 00 83 26             68 	int _EXTI_PORTC_IRQHandler ; int5
      008020 82 00 83 27             69 	int _EXTI_PORTD_IRQHandler ; int6
      008024 82 00 83 28             70 	int _EXTI_PORTE_IRQHandler ; int7
      008028 82 00 83 29             71 	int _CAN_RX_IRQHandler ; int8
      00802C 82 00 83 2A             72 	int _CAN_TX_IRQHandler ; int9
      008030 82 00 83 2B             73 	int _SPI_IRQHandler ; int10
      008034 82 00 83 2C             74 	int _TIM1_UPD_OVF_TRG_BRK_IRQHandler ; int11
      008038 82 00 83 2D             75 	int _TIM1_CAP_COM_IRQHandler ; int12
      00803C 82 00 83 2E             76 	int _TIM2_UPD_OVF_BRK_IRQHandler ; int13
      008040 82 00 83 4A             77 	int _TIM2_CAP_COM_IRQHandler ; int14
      008044 82 00 83 4B             78 	int _TIM3_UPD_OVF_BRK_IRQHandler ; int15
      008048 82 00 83 4C             79 	int _TIM3_CAP_COM_IRQHandler ; int16
      00804C 82 00 83 4D             80 	int _UART1_TX_IRQHandler ; int17
      008050 82 00 83 4E             81 	int _UART1_RX_IRQHandler ; int18
      008054 82 00 83 4F             82 	int _I2C_IRQHandler ; int19
      008058 82 00 83 50             83 	int _UART3_TX_IRQHandler ; int20
      00805C 82 00 83 51             84 	int _UART3_RX_IRQHandler ; int21
      008060 82 00 83 52             85 	int _ADC2_IRQHandler ; int22
      008064 82 00 83 53             86 	int _TIM4_UPD_OVF_IRQHandler ; int23
      008068 82 00 83 6D             87 	int _EEPROM_EEC_IRQHandler ; int24
                                     88 ;--------------------------------------------------------
                                     89 ; global & static initialisations
                                     90 ;--------------------------------------------------------
                                     91 	.area HOME
                                     92 	.area GSINIT
                                     93 	.area GSFINAL
                                     94 	.area GSINIT
      00806F CD 85 12         [ 4]   95 	call	___sdcc_external_startup
      008072 4D               [ 1]   96 	tnz	a
      008073 27 03            [ 1]   97 	jreq	__sdcc_init_data
      008075 CC 80 6C         [ 2]   98 	jp	__sdcc_program_startup
      008078                         99 __sdcc_init_data:
                                    100 ; stm8_genXINIT() start
      008078 AE 00 00         [ 2]  101 	ldw x, #l_DATA
      00807B 27 07            [ 1]  102 	jreq	00002$
      00807D                        103 00001$:
      00807D 72 4F 00 00      [ 1]  104 	clr (s_DATA - 1, x)
      008081 5A               [ 2]  105 	decw x
      008082 26 F9            [ 1]  106 	jrne	00001$
      008084                        107 00002$:
      008084 AE 00 08         [ 2]  108 	ldw	x, #l_INITIALIZER
      008087 27 09            [ 1]  109 	jreq	00004$
      008089                        110 00003$:
      008089 D6 80 94         [ 1]  111 	ld	a, (s_INITIALIZER - 1, x)
      00808C D7 00 00         [ 1]  112 	ld	(s_INITIALIZED - 1, x), a
      00808F 5A               [ 2]  113 	decw	x
      008090 26 F7            [ 1]  114 	jrne	00003$
      008092                        115 00004$:
                                    116 ; stm8_genXINIT() end
                                    117 	.area GSFINAL
      008092 CC 80 6C         [ 2]  118 	jp	__sdcc_program_startup
                                    119 ;--------------------------------------------------------
                                    120 ; Home
                                    121 ;--------------------------------------------------------
                                    122 	.area HOME
                                    123 	.area HOME
      00806C                        124 __sdcc_program_startup:
      00806C CC 82 6C         [ 2]  125 	jp	_main
                                    126 ;	return from main will return to caller
                                    127 ;--------------------------------------------------------
                                    128 ; code
                                    129 ;--------------------------------------------------------
                                    130 	.area CODE
                                    131 ;	./src/main.c: 24: void max7219_send(uint8_t address, uint8_t data) {
                                    132 ; genLabel
                                    133 ;	-----------------------------------------
                                    134 ;	 function max7219_send
                                    135 ;	-----------------------------------------
                                    136 ;	Register assignment is optimal.
                                    137 ;	Stack space usage: 2 bytes.
      008164                        138 _max7219_send:
      008164 89               [ 2]  139 	pushw	x
                                    140 ; genReceive
      008165 6B 01            [ 1]  141 	ld	(0x01, sp), a
                                    142 ;	./src/main.c: 26: CS_LOW;
                                    143 ; genSend
      008167 A6 02            [ 1]  144 	ld	a, #0x02
                                    145 ; genSend
      008169 AE 50 05         [ 2]  146 	ldw	x, #0x5005
                                    147 ; genCall
      00816C CD 84 EA         [ 4]  148 	call	_GPIO_WriteLow
                                    149 ;	./src/main.c: 27: uint8_t mask = 0b10000000;
                                    150 ; genAssign
      00816F A6 80            [ 1]  151 	ld	a, #0x80
      008171 6B 02            [ 1]  152 	ld	(0x02, sp), a
                                    153 ;	./src/main.c: 28: CLK_LOW;
                                    154 ; genSend
      008173 A6 01            [ 1]  155 	ld	a, #0x01
                                    156 ; genSend
      008175 AE 50 05         [ 2]  157 	ldw	x, #0x5005
                                    158 ; genCall
      008178 CD 84 EA         [ 4]  159 	call	_GPIO_WriteLow
                                    160 ;	./src/main.c: 29: while (mask) {
                                    161 ; genLabel
      00817B                        162 00104$:
                                    163 ; genIfx
      00817B 0D 02            [ 1]  164 	tnz	(0x02, sp)
      00817D 26 03            [ 1]  165 	jrne	00157$
      00817F CC 81 B4         [ 2]  166 	jp	00106$
      008182                        167 00157$:
                                    168 ;	./src/main.c: 30: if (mask & address) {
                                    169 ; genAnd
      008182 7B 02            [ 1]  170 	ld	a, (0x02, sp)
      008184 14 01            [ 1]  171 	and	a, (0x01, sp)
                                    172 ; genIfx
      008186 4D               [ 1]  173 	tnz	a
      008187 26 03            [ 1]  174 	jrne	00158$
      008189 CC 81 97         [ 2]  175 	jp	00102$
      00818C                        176 00158$:
                                    177 ;	./src/main.c: 31: DATA_HIGH;
                                    178 ; genSend
      00818C A6 04            [ 1]  179 	ld	a, #0x04
                                    180 ; genSend
      00818E AE 50 05         [ 2]  181 	ldw	x, #0x5005
                                    182 ; genCall
      008191 CD 86 3E         [ 4]  183 	call	_GPIO_WriteHigh
                                    184 ; genGoto
      008194 CC 81 9F         [ 2]  185 	jp	00103$
                                    186 ; genLabel
      008197                        187 00102$:
                                    188 ;	./src/main.c: 33: DATA_LOW;
                                    189 ; genSend
      008197 A6 04            [ 1]  190 	ld	a, #0x04
                                    191 ; genSend
      008199 AE 50 05         [ 2]  192 	ldw	x, #0x5005
                                    193 ; genCall
      00819C CD 84 EA         [ 4]  194 	call	_GPIO_WriteLow
                                    195 ; genLabel
      00819F                        196 00103$:
                                    197 ;	./src/main.c: 35: CLK_HIGH;
                                    198 ; genSend
      00819F A6 01            [ 1]  199 	ld	a, #0x01
                                    200 ; genSend
      0081A1 AE 50 05         [ 2]  201 	ldw	x, #0x5005
                                    202 ; genCall
      0081A4 CD 86 3E         [ 4]  203 	call	_GPIO_WriteHigh
                                    204 ;	./src/main.c: 36: mask = mask >> 1;
                                    205 ; genRightShiftLiteral
      0081A7 04 02            [ 1]  206 	srl	(0x02, sp)
                                    207 ;	./src/main.c: 37: CLK_LOW;
                                    208 ; genSend
      0081A9 A6 01            [ 1]  209 	ld	a, #0x01
                                    210 ; genSend
      0081AB AE 50 05         [ 2]  211 	ldw	x, #0x5005
                                    212 ; genCall
      0081AE CD 84 EA         [ 4]  213 	call	_GPIO_WriteLow
                                    214 ; genGoto
      0081B1 CC 81 7B         [ 2]  215 	jp	00104$
                                    216 ; genLabel
      0081B4                        217 00106$:
                                    218 ;	./src/main.c: 40: mask = 0b10000000;
                                    219 ; genAssign
      0081B4 A6 80            [ 1]  220 	ld	a, #0x80
      0081B6 6B 02            [ 1]  221 	ld	(0x02, sp), a
                                    222 ;	./src/main.c: 41: while (mask) {
                                    223 ; genLabel
      0081B8                        224 00110$:
                                    225 ; genIfx
      0081B8 0D 02            [ 1]  226 	tnz	(0x02, sp)
      0081BA 26 03            [ 1]  227 	jrne	00159$
      0081BC CC 81 F1         [ 2]  228 	jp	00112$
      0081BF                        229 00159$:
                                    230 ;	./src/main.c: 42: if (mask & data) {
                                    231 ; genAnd
      0081BF 7B 02            [ 1]  232 	ld	a, (0x02, sp)
      0081C1 14 05            [ 1]  233 	and	a, (0x05, sp)
                                    234 ; genIfx
      0081C3 4D               [ 1]  235 	tnz	a
      0081C4 26 03            [ 1]  236 	jrne	00160$
      0081C6 CC 81 D4         [ 2]  237 	jp	00108$
      0081C9                        238 00160$:
                                    239 ;	./src/main.c: 43: DATA_HIGH;
                                    240 ; genSend
      0081C9 A6 04            [ 1]  241 	ld	a, #0x04
                                    242 ; genSend
      0081CB AE 50 05         [ 2]  243 	ldw	x, #0x5005
                                    244 ; genCall
      0081CE CD 86 3E         [ 4]  245 	call	_GPIO_WriteHigh
                                    246 ; genGoto
      0081D1 CC 81 DC         [ 2]  247 	jp	00109$
                                    248 ; genLabel
      0081D4                        249 00108$:
                                    250 ;	./src/main.c: 45: DATA_LOW;
                                    251 ; genSend
      0081D4 A6 04            [ 1]  252 	ld	a, #0x04
                                    253 ; genSend
      0081D6 AE 50 05         [ 2]  254 	ldw	x, #0x5005
                                    255 ; genCall
      0081D9 CD 84 EA         [ 4]  256 	call	_GPIO_WriteLow
                                    257 ; genLabel
      0081DC                        258 00109$:
                                    259 ;	./src/main.c: 47: CLK_HIGH;
                                    260 ; genSend
      0081DC A6 01            [ 1]  261 	ld	a, #0x01
                                    262 ; genSend
      0081DE AE 50 05         [ 2]  263 	ldw	x, #0x5005
                                    264 ; genCall
      0081E1 CD 86 3E         [ 4]  265 	call	_GPIO_WriteHigh
                                    266 ;	./src/main.c: 48: mask = mask >> 1;
                                    267 ; genRightShiftLiteral
      0081E4 04 02            [ 1]  268 	srl	(0x02, sp)
                                    269 ;	./src/main.c: 49: CLK_LOW;
                                    270 ; genSend
      0081E6 A6 01            [ 1]  271 	ld	a, #0x01
                                    272 ; genSend
      0081E8 AE 50 05         [ 2]  273 	ldw	x, #0x5005
                                    274 ; genCall
      0081EB CD 84 EA         [ 4]  275 	call	_GPIO_WriteLow
                                    276 ; genGoto
      0081EE CC 81 B8         [ 2]  277 	jp	00110$
                                    278 ; genLabel
      0081F1                        279 00112$:
                                    280 ;	./src/main.c: 52: CS_HIGH;
                                    281 ; genSend
      0081F1 A6 02            [ 1]  282 	ld	a, #0x02
                                    283 ; genSend
      0081F3 AE 50 05         [ 2]  284 	ldw	x, #0x5005
                                    285 ; genCall
      0081F6 CD 86 3E         [ 4]  286 	call	_GPIO_WriteHigh
                                    287 ; genLabel
      0081F9                        288 00113$:
                                    289 ;	./src/main.c: 53: }
                                    290 ; genEndFunction
      0081F9 85               [ 2]  291 	popw	x
      0081FA 85               [ 2]  292 	popw	x
      0081FB 84               [ 1]  293 	pop	a
      0081FC FC               [ 2]  294 	jp	(x)
                                    295 ;	./src/main.c: 54: void TIM2_init(void) {
                                    296 ; genLabel
                                    297 ;	-----------------------------------------
                                    298 ;	 function TIM2_init
                                    299 ;	-----------------------------------------
                                    300 ;	Register assignment is optimal.
                                    301 ;	Stack space usage: 0 bytes.
      0081FD                        302 _TIM2_init:
                                    303 ;	./src/main.c: 55: CLK_PeripheralClockConfig(CLK_PERIPHERAL_TIMER2, ENABLE);
                                    304 ; genIPush
      0081FD 4B 01            [ 1]  305 	push	#0x01
                                    306 ; genSend
      0081FF A6 05            [ 1]  307 	ld	a, #0x05
                                    308 ; genCall
      008201 CD 84 3C         [ 4]  309 	call	_CLK_PeripheralClockConfig
                                    310 ;	./src/main.c: 56: TIM2_TimeBaseInit(TIM2_PRESCALER_16, 999);
                                    311 ; genSend
      008204 AE 03 E7         [ 2]  312 	ldw	x, #0x03e7
                                    313 ; genSend
      008207 A6 04            [ 1]  314 	ld	a, #0x04
                                    315 ; genCall
      008209 CD 86 32         [ 4]  316 	call	_TIM2_TimeBaseInit
                                    317 ;	./src/main.c: 57: TIM2_ClearFlag(TIM2_FLAG_UPDATE);
                                    318 ; genSend
      00820C 5F               [ 1]  319 	clrw	x
      00820D 5C               [ 1]  320 	incw	x
                                    321 ; genCall
      00820E CD 86 53         [ 4]  322 	call	_TIM2_ClearFlag
                                    323 ;	./src/main.c: 58: TIM2_ITConfig(TIM2_IT_UPDATE, ENABLE);
                                    324 ; genIPush
      008211 4B 01            [ 1]  325 	push	#0x01
                                    326 ; genSend
      008213 A6 01            [ 1]  327 	ld	a, #0x01
                                    328 ; genCall
      008215 CD 83 F8         [ 4]  329 	call	_TIM2_ITConfig
                                    330 ;	./src/main.c: 59: TIM2_Cmd(ENABLE);
                                    331 ; genSend
      008218 A6 01            [ 1]  332 	ld	a, #0x01
                                    333 ; genCall
      00821A CC 84 F6         [ 2]  334 	jp	_TIM2_Cmd
                                    335 ; genLabel
      00821D                        336 00101$:
                                    337 ;	./src/main.c: 60: }
                                    338 ; genEndFunction
      00821D 81               [ 4]  339 	ret
                                    340 ;	./src/main.c: 62: void max7219_init(void) {
                                    341 ; genLabel
                                    342 ;	-----------------------------------------
                                    343 ;	 function max7219_init
                                    344 ;	-----------------------------------------
                                    345 ;	Register assignment is optimal.
                                    346 ;	Stack space usage: 0 bytes.
      00821E                        347 _max7219_init:
                                    348 ;	./src/main.c: 63: GPIO_Init(CS_GPIO, CS_PIN, GPIO_MODE_OUT_PP_LOW_SLOW);
                                    349 ; genIPush
      00821E 4B C0            [ 1]  350 	push	#0xc0
                                    351 ; genSend
      008220 A6 02            [ 1]  352 	ld	a, #0x02
                                    353 ; genSend
      008222 AE 50 05         [ 2]  354 	ldw	x, #0x5005
                                    355 ; genCall
      008225 CD 83 6E         [ 4]  356 	call	_GPIO_Init
                                    357 ;	./src/main.c: 64: GPIO_Init(CLK_GPIO, CLK_PIN, GPIO_MODE_OUT_PP_LOW_SLOW);
                                    358 ; genIPush
      008228 4B C0            [ 1]  359 	push	#0xc0
                                    360 ; genSend
      00822A A6 01            [ 1]  361 	ld	a, #0x01
                                    362 ; genSend
      00822C AE 50 05         [ 2]  363 	ldw	x, #0x5005
                                    364 ; genCall
      00822F CD 83 6E         [ 4]  365 	call	_GPIO_Init
                                    366 ;	./src/main.c: 65: GPIO_Init(DATA_GPIO, DATA_PIN, GPIO_MODE_OUT_PP_LOW_SLOW);
                                    367 ; genIPush
      008232 4B C0            [ 1]  368 	push	#0xc0
                                    369 ; genSend
      008234 A6 04            [ 1]  370 	ld	a, #0x04
                                    371 ; genSend
      008236 AE 50 05         [ 2]  372 	ldw	x, #0x5005
                                    373 ; genCall
      008239 CD 83 6E         [ 4]  374 	call	_GPIO_Init
                                    375 ;	./src/main.c: 67: max7219_send(DECODE_MODE, DECODE_ALL);        // dekodér
                                    376 ; genIPush
      00823C 4B FF            [ 1]  377 	push	#0xff
                                    378 ; genSend
      00823E A6 09            [ 1]  379 	ld	a, #0x09
                                    380 ; genCall
      008240 CD 81 64         [ 4]  381 	call	_max7219_send
                                    382 ;	./src/main.c: 68: max7219_send(SCAN_LIMIT, 3);                  // Kolik cifer zapneme
                                    383 ; genIPush
      008243 4B 03            [ 1]  384 	push	#0x03
                                    385 ; genSend
      008245 A6 0B            [ 1]  386 	ld	a, #0x0b
                                    387 ; genCall
      008247 CD 81 64         [ 4]  388 	call	_max7219_send
                                    389 ;	./src/main.c: 69: max7219_send(INTENSITY, 5);                   // Jas
                                    390 ; genIPush
      00824A 4B 05            [ 1]  391 	push	#0x05
                                    392 ; genSend
      00824C A6 0A            [ 1]  393 	ld	a, #0x0a
                                    394 ; genCall
      00824E CD 81 64         [ 4]  395 	call	_max7219_send
                                    396 ;	./src/main.c: 70: max7219_send(DISPLAY_TEST, DISPLAY_TEST_OFF); // test displeje
                                    397 ; genIPush
      008251 4B 00            [ 1]  398 	push	#0x00
                                    399 ; genSend
      008253 A6 0F            [ 1]  400 	ld	a, #0x0f
                                    401 ; genCall
      008255 CD 81 64         [ 4]  402 	call	_max7219_send
                                    403 ;	./src/main.c: 71: max7219_send(SHUTDOWN, SHUTDOWN_ON);          // On/OFF
                                    404 ; genIPush
      008258 4B 01            [ 1]  405 	push	#0x01
                                    406 ; genSend
      00825A A6 0C            [ 1]  407 	ld	a, #0x0c
                                    408 ; genCall
      00825C CD 81 64         [ 4]  409 	call	_max7219_send
                                    410 ; genLabel
      00825F                        411 00101$:
                                    412 ;	./src/main.c: 72: }
                                    413 ; genEndFunction
      00825F 81               [ 4]  414 	ret
                                    415 ;	./src/main.c: 74: void setup(void) {
                                    416 ; genLabel
                                    417 ;	-----------------------------------------
                                    418 ;	 function setup
                                    419 ;	-----------------------------------------
                                    420 ;	Register assignment is optimal.
                                    421 ;	Stack space usage: 0 bytes.
      008260                        422 _setup:
                                    423 ;	./src/main.c: 75: CLK_HSIPrescalerConfig(CLK_PRESCALER_HSIDIV1); // taktovat MCU na 16MHz
                                    424 ; genSend
      008260 4F               [ 1]  425 	clr	a
                                    426 ; genCall
      008261 CD 85 30         [ 4]  427 	call	_CLK_HSIPrescalerConfig
                                    428 ;	./src/main.c: 78: max7219_init();
                                    429 ; genCall
      008264 CD 82 1E         [ 4]  430 	call	_max7219_init
                                    431 ;	./src/main.c: 79: enableInterrupts();
                                    432 ;	genInline
      008267 9A               [ 1]  433 	rim
                                    434 ;	./src/main.c: 80: TIM2_init();
                                    435 ; genCall
      008268 CC 81 FD         [ 2]  436 	jp	_TIM2_init
                                    437 ; genLabel
      00826B                        438 00101$:
                                    439 ;	./src/main.c: 81: }
                                    440 ; genEndFunction
      00826B 81               [ 4]  441 	ret
                                    442 ;	./src/main.c: 83: int main(void)
                                    443 ; genLabel
                                    444 ;	-----------------------------------------
                                    445 ;	 function main
                                    446 ;	-----------------------------------------
                                    447 ;	Register assignment might be sub-optimal.
                                    448 ;	Stack space usage: 9 bytes.
      00826C                        449 _main:
      00826C 52 09            [ 2]  450 	sub	sp, #9
                                    451 ;	./src/main.c: 86: setup();
                                    452 ; genCall
      00826E CD 82 60         [ 4]  453 	call	_setup
                                    454 ;	./src/main.c: 89: max7219_send(DIGIT0, 0);
                                    455 ; genIPush
      008271 4B 00            [ 1]  456 	push	#0x00
                                    457 ; genSend
      008273 A6 01            [ 1]  458 	ld	a, #0x01
                                    459 ; genCall
      008275 CD 81 64         [ 4]  460 	call	_max7219_send
                                    461 ;	./src/main.c: 92: uint32_t time = 0;
                                    462 ; genAssign
      008278 5F               [ 1]  463 	clrw	x
      008279 1F 03            [ 2]  464 	ldw	(0x03, sp), x
      00827B 1F 01            [ 2]  465 	ldw	(0x01, sp), x
                                    466 ;	./src/main.c: 93: uint8_t jednotky = 0;
                                    467 ; genAssign
      00827D 0F 09            [ 1]  468 	clr	(0x09, sp)
                                    469 ;	./src/main.c: 98: while (1)
                                    470 ; genLabel
      00827F                        471 00106$:
                                    472 ;	./src/main.c: 100: if ((svujcas - time) > 1000)
                                    473 ; genMinus
      00827F CE 00 03         [ 2]  474 	ldw	x, _svujcas+2
      008282 72 F0 03         [ 2]  475 	subw	x, (0x03, sp)
      008285 1F 07            [ 2]  476 	ldw	(0x07, sp), x
      008287 C6 00 02         [ 1]  477 	ld	a, _svujcas+1
      00828A 12 02            [ 1]  478 	sbc	a, (0x02, sp)
      00828C 6B 06            [ 1]  479 	ld	(0x06, sp), a
      00828E C6 00 01         [ 1]  480 	ld	a, _svujcas+0
      008291 12 01            [ 1]  481 	sbc	a, (0x01, sp)
      008293 6B 05            [ 1]  482 	ld	(0x05, sp), a
                                    483 ; genCmp
                                    484 ; genCmpTnz
      008295 AE 03 E8         [ 2]  485 	ldw	x, #0x03e8
      008298 13 07            [ 2]  486 	cpw	x, (0x07, sp)
      00829A 4F               [ 1]  487 	clr	a
      00829B 12 06            [ 1]  488 	sbc	a, (0x06, sp)
      00829D 4F               [ 1]  489 	clr	a
      00829E 12 05            [ 1]  490 	sbc	a, (0x05, sp)
      0082A0 25 03            [ 1]  491 	jrc	00131$
      0082A2 CC 82 7F         [ 2]  492 	jp	00106$
      0082A5                        493 00131$:
                                    494 ; skipping generated iCode
                                    495 ;	./src/main.c: 102: time = svujcas;
                                    496 ; genAssign
      0082A5 CE 00 03         [ 2]  497 	ldw	x, _svujcas+2
      0082A8 1F 03            [ 2]  498 	ldw	(0x03, sp), x
      0082AA CE 00 01         [ 2]  499 	ldw	x, _svujcas+0
      0082AD 1F 01            [ 2]  500 	ldw	(0x01, sp), x
                                    501 ;	./src/main.c: 103: max7219_send(DIGIT0, jednotky);
                                    502 ; genIPush
      0082AF 7B 09            [ 1]  503 	ld	a, (0x09, sp)
      0082B1 88               [ 1]  504 	push	a
                                    505 ; genSend
      0082B2 A6 01            [ 1]  506 	ld	a, #0x01
                                    507 ; genCall
      0082B4 CD 81 64         [ 4]  508 	call	_max7219_send
                                    509 ;	./src/main.c: 104: max7219_send(DIGIT1, 0);
                                    510 ; genIPush
      0082B7 4B 00            [ 1]  511 	push	#0x00
                                    512 ; genSend
      0082B9 A6 02            [ 1]  513 	ld	a, #0x02
                                    514 ; genCall
      0082BB CD 81 64         [ 4]  515 	call	_max7219_send
                                    516 ;	./src/main.c: 105: max7219_send(DIGIT2, 0);
                                    517 ; genIPush
      0082BE 4B 00            [ 1]  518 	push	#0x00
                                    519 ; genSend
      0082C0 A6 03            [ 1]  520 	ld	a, #0x03
                                    521 ; genCall
      0082C2 CD 81 64         [ 4]  522 	call	_max7219_send
                                    523 ;	./src/main.c: 106: max7219_send(DIGIT3, 0);
                                    524 ; genIPush
      0082C5 4B 00            [ 1]  525 	push	#0x00
                                    526 ; genSend
      0082C7 A6 04            [ 1]  527 	ld	a, #0x04
                                    528 ; genCall
      0082C9 CD 81 64         [ 4]  529 	call	_max7219_send
                                    530 ;	./src/main.c: 109: jednotky++;
                                    531 ; genPlus
      0082CC 0C 09            [ 1]  532 	inc	(0x09, sp)
                                    533 ;	./src/main.c: 110: if (jednotky>9){
                                    534 ; genCmp
                                    535 ; genCmpTnz
      0082CE 7B 09            [ 1]  536 	ld	a, (0x09, sp)
      0082D0 A1 09            [ 1]  537 	cp	a, #0x09
      0082D2 22 03            [ 1]  538 	jrugt	00132$
      0082D4 CC 82 7F         [ 2]  539 	jp	00106$
      0082D7                        540 00132$:
                                    541 ; skipping generated iCode
                                    542 ;	./src/main.c: 111: jednotky=0;
                                    543 ; genAssign
      0082D7 0F 09            [ 1]  544 	clr	(0x09, sp)
                                    545 ; genGoto
      0082D9 CC 82 7F         [ 2]  546 	jp	00106$
                                    547 ; genLabel
      0082DC                        548 00108$:
                                    549 ;	./src/main.c: 120: }
                                    550 ; genEndFunction
      0082DC 5B 09            [ 2]  551 	addw	sp, #9
      0082DE 81               [ 4]  552 	ret
                                    553 	.area CODE
                                    554 	.area CONST
                                    555 	.area INITIALIZER
      008095                        556 __xinit__svujcas:
      008095 00 00 00 00            557 	.byte #0x00, #0x00, #0x00, #0x00	; 0
                                    558 	.area CABS (ABS)
