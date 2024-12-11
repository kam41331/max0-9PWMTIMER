                                      1 ;--------------------------------------------------------
                                      2 ; File Created by SDCC : free open source ISO C Compiler 
                                      3 ; Version 4.4.0 #14620 (Linux)
                                      4 ;--------------------------------------------------------
                                      5 	.module stm8s_it
                                      6 	.optsdcc -mstm8
                                      7 	
                                      8 ;--------------------------------------------------------
                                      9 ; Public variables in this module
                                     10 ;--------------------------------------------------------
                                     11 	.globl _TIM4_ClearFlag
                                     12 	.globl _TIM2_ClearFlag
                                     13 	.globl _TRAP_IRQHandler
                                     14 	.globl _TLI_IRQHandler
                                     15 	.globl _AWU_IRQHandler
                                     16 	.globl _CLK_IRQHandler
                                     17 	.globl _EXTI_PORTA_IRQHandler
                                     18 	.globl _EXTI_PORTB_IRQHandler
                                     19 	.globl _EXTI_PORTC_IRQHandler
                                     20 	.globl _EXTI_PORTD_IRQHandler
                                     21 	.globl _EXTI_PORTE_IRQHandler
                                     22 	.globl _CAN_RX_IRQHandler
                                     23 	.globl _CAN_TX_IRQHandler
                                     24 	.globl _SPI_IRQHandler
                                     25 	.globl _TIM1_UPD_OVF_TRG_BRK_IRQHandler
                                     26 	.globl _TIM1_CAP_COM_IRQHandler
                                     27 	.globl _TIM2_UPD_OVF_BRK_IRQHandler
                                     28 	.globl _TIM2_CAP_COM_IRQHandler
                                     29 	.globl _TIM3_UPD_OVF_BRK_IRQHandler
                                     30 	.globl _TIM3_CAP_COM_IRQHandler
                                     31 	.globl _UART1_TX_IRQHandler
                                     32 	.globl _UART1_RX_IRQHandler
                                     33 	.globl _I2C_IRQHandler
                                     34 	.globl _UART3_TX_IRQHandler
                                     35 	.globl _UART3_RX_IRQHandler
                                     36 	.globl _ADC2_IRQHandler
                                     37 	.globl _TIM4_UPD_OVF_IRQHandler
                                     38 	.globl _EEPROM_EEC_IRQHandler
                                     39 ;--------------------------------------------------------
                                     40 ; ram data
                                     41 ;--------------------------------------------------------
                                     42 	.area DATA
                                     43 ;--------------------------------------------------------
                                     44 ; ram data
                                     45 ;--------------------------------------------------------
                                     46 	.area INITIALIZED
                                     47 ;--------------------------------------------------------
                                     48 ; absolute external ram data
                                     49 ;--------------------------------------------------------
                                     50 	.area DABS (ABS)
                                     51 
                                     52 ; default segment ordering for linker
                                     53 	.area HOME
                                     54 	.area GSINIT
                                     55 	.area GSFINAL
                                     56 	.area CONST
                                     57 	.area INITIALIZER
                                     58 	.area CODE
                                     59 
                                     60 ;--------------------------------------------------------
                                     61 ; global & static initialisations
                                     62 ;--------------------------------------------------------
                                     63 	.area HOME
                                     64 	.area GSINIT
                                     65 	.area GSFINAL
                                     66 	.area GSINIT
                                     67 ;--------------------------------------------------------
                                     68 ; Home
                                     69 ;--------------------------------------------------------
                                     70 	.area HOME
                                     71 	.area HOME
                                     72 ;--------------------------------------------------------
                                     73 ; code
                                     74 ;--------------------------------------------------------
                                     75 	.area CODE
                                     76 ;	./src/stm8s_it.c: 66: INTERRUPT_HANDLER_TRAP(TRAP_IRQHandler)
                                     77 ; genLabel
                                     78 ;	-----------------------------------------
                                     79 ;	 function TRAP_IRQHandler
                                     80 ;	-----------------------------------------
                                     81 ;	Register assignment is optimal.
                                     82 ;	Stack space usage: 0 bytes.
      008320                         83 _TRAP_IRQHandler:
                                     84 ;	./src/stm8s_it.c: 71: }
                                     85 ; genLabel
      008320                         86 00101$:
                                     87 ; genEndFunction
      008320 80               [11]   88 	iret
                                     89 ;	./src/stm8s_it.c: 77: INTERRUPT_HANDLER(TLI_IRQHandler, 0)
                                     90 ; genLabel
                                     91 ;	-----------------------------------------
                                     92 ;	 function TLI_IRQHandler
                                     93 ;	-----------------------------------------
                                     94 ;	Register assignment is optimal.
                                     95 ;	Stack space usage: 0 bytes.
      008321                         96 _TLI_IRQHandler:
                                     97 ;	./src/stm8s_it.c: 82: }
                                     98 ; genLabel
      008321                         99 00101$:
                                    100 ; genEndFunction
      008321 80               [11]  101 	iret
                                    102 ;	./src/stm8s_it.c: 89: INTERRUPT_HANDLER(AWU_IRQHandler, 1)
                                    103 ; genLabel
                                    104 ;	-----------------------------------------
                                    105 ;	 function AWU_IRQHandler
                                    106 ;	-----------------------------------------
                                    107 ;	Register assignment is optimal.
                                    108 ;	Stack space usage: 0 bytes.
      008322                        109 _AWU_IRQHandler:
                                    110 ;	./src/stm8s_it.c: 94: }
                                    111 ; genLabel
      008322                        112 00101$:
                                    113 ; genEndFunction
      008322 80               [11]  114 	iret
                                    115 ;	./src/stm8s_it.c: 101: INTERRUPT_HANDLER(CLK_IRQHandler, 2)
                                    116 ; genLabel
                                    117 ;	-----------------------------------------
                                    118 ;	 function CLK_IRQHandler
                                    119 ;	-----------------------------------------
                                    120 ;	Register assignment is optimal.
                                    121 ;	Stack space usage: 0 bytes.
      008323                        122 _CLK_IRQHandler:
                                    123 ;	./src/stm8s_it.c: 106: }
                                    124 ; genLabel
      008323                        125 00101$:
                                    126 ; genEndFunction
      008323 80               [11]  127 	iret
                                    128 ;	./src/stm8s_it.c: 113: INTERRUPT_HANDLER(EXTI_PORTA_IRQHandler, 3)
                                    129 ; genLabel
                                    130 ;	-----------------------------------------
                                    131 ;	 function EXTI_PORTA_IRQHandler
                                    132 ;	-----------------------------------------
                                    133 ;	Register assignment is optimal.
                                    134 ;	Stack space usage: 0 bytes.
      008324                        135 _EXTI_PORTA_IRQHandler:
                                    136 ;	./src/stm8s_it.c: 118: }
                                    137 ; genLabel
      008324                        138 00101$:
                                    139 ; genEndFunction
      008324 80               [11]  140 	iret
                                    141 ;	./src/stm8s_it.c: 125: INTERRUPT_HANDLER(EXTI_PORTB_IRQHandler, 4)
                                    142 ; genLabel
                                    143 ;	-----------------------------------------
                                    144 ;	 function EXTI_PORTB_IRQHandler
                                    145 ;	-----------------------------------------
                                    146 ;	Register assignment is optimal.
                                    147 ;	Stack space usage: 0 bytes.
      008325                        148 _EXTI_PORTB_IRQHandler:
                                    149 ;	./src/stm8s_it.c: 130: }
                                    150 ; genLabel
      008325                        151 00101$:
                                    152 ; genEndFunction
      008325 80               [11]  153 	iret
                                    154 ;	./src/stm8s_it.c: 137: INTERRUPT_HANDLER(EXTI_PORTC_IRQHandler, 5)
                                    155 ; genLabel
                                    156 ;	-----------------------------------------
                                    157 ;	 function EXTI_PORTC_IRQHandler
                                    158 ;	-----------------------------------------
                                    159 ;	Register assignment is optimal.
                                    160 ;	Stack space usage: 0 bytes.
      008326                        161 _EXTI_PORTC_IRQHandler:
                                    162 ;	./src/stm8s_it.c: 142: }
                                    163 ; genLabel
      008326                        164 00101$:
                                    165 ; genEndFunction
      008326 80               [11]  166 	iret
                                    167 ;	./src/stm8s_it.c: 149: INTERRUPT_HANDLER(EXTI_PORTD_IRQHandler, 6)
                                    168 ; genLabel
                                    169 ;	-----------------------------------------
                                    170 ;	 function EXTI_PORTD_IRQHandler
                                    171 ;	-----------------------------------------
                                    172 ;	Register assignment is optimal.
                                    173 ;	Stack space usage: 0 bytes.
      008327                        174 _EXTI_PORTD_IRQHandler:
                                    175 ;	./src/stm8s_it.c: 154: }
                                    176 ; genLabel
      008327                        177 00101$:
                                    178 ; genEndFunction
      008327 80               [11]  179 	iret
                                    180 ;	./src/stm8s_it.c: 161: INTERRUPT_HANDLER(EXTI_PORTE_IRQHandler, 7)
                                    181 ; genLabel
                                    182 ;	-----------------------------------------
                                    183 ;	 function EXTI_PORTE_IRQHandler
                                    184 ;	-----------------------------------------
                                    185 ;	Register assignment is optimal.
                                    186 ;	Stack space usage: 0 bytes.
      008328                        187 _EXTI_PORTE_IRQHandler:
                                    188 ;	./src/stm8s_it.c: 166: }
                                    189 ; genLabel
      008328                        190 00101$:
                                    191 ; genEndFunction
      008328 80               [11]  192 	iret
                                    193 ;	./src/stm8s_it.c: 187: INTERRUPT_HANDLER(CAN_RX_IRQHandler, 8)
                                    194 ; genLabel
                                    195 ;	-----------------------------------------
                                    196 ;	 function CAN_RX_IRQHandler
                                    197 ;	-----------------------------------------
                                    198 ;	Register assignment is optimal.
                                    199 ;	Stack space usage: 0 bytes.
      008329                        200 _CAN_RX_IRQHandler:
                                    201 ;	./src/stm8s_it.c: 192: }
                                    202 ; genLabel
      008329                        203 00101$:
                                    204 ; genEndFunction
      008329 80               [11]  205 	iret
                                    206 ;	./src/stm8s_it.c: 199: INTERRUPT_HANDLER(CAN_TX_IRQHandler, 9)
                                    207 ; genLabel
                                    208 ;	-----------------------------------------
                                    209 ;	 function CAN_TX_IRQHandler
                                    210 ;	-----------------------------------------
                                    211 ;	Register assignment is optimal.
                                    212 ;	Stack space usage: 0 bytes.
      00832A                        213 _CAN_TX_IRQHandler:
                                    214 ;	./src/stm8s_it.c: 204: }
                                    215 ; genLabel
      00832A                        216 00101$:
                                    217 ; genEndFunction
      00832A 80               [11]  218 	iret
                                    219 ;	./src/stm8s_it.c: 212: INTERRUPT_HANDLER(SPI_IRQHandler, 10)
                                    220 ; genLabel
                                    221 ;	-----------------------------------------
                                    222 ;	 function SPI_IRQHandler
                                    223 ;	-----------------------------------------
                                    224 ;	Register assignment is optimal.
                                    225 ;	Stack space usage: 0 bytes.
      00832B                        226 _SPI_IRQHandler:
                                    227 ;	./src/stm8s_it.c: 217: }
                                    228 ; genLabel
      00832B                        229 00101$:
                                    230 ; genEndFunction
      00832B 80               [11]  231 	iret
                                    232 ;	./src/stm8s_it.c: 224: INTERRUPT_HANDLER(TIM1_UPD_OVF_TRG_BRK_IRQHandler, 11)
                                    233 ; genLabel
                                    234 ;	-----------------------------------------
                                    235 ;	 function TIM1_UPD_OVF_TRG_BRK_IRQHandler
                                    236 ;	-----------------------------------------
                                    237 ;	Register assignment is optimal.
                                    238 ;	Stack space usage: 0 bytes.
      00832C                        239 _TIM1_UPD_OVF_TRG_BRK_IRQHandler:
                                    240 ;	./src/stm8s_it.c: 229: }
                                    241 ; genLabel
      00832C                        242 00101$:
                                    243 ; genEndFunction
      00832C 80               [11]  244 	iret
                                    245 ;	./src/stm8s_it.c: 236: INTERRUPT_HANDLER(TIM1_CAP_COM_IRQHandler, 12)
                                    246 ; genLabel
                                    247 ;	-----------------------------------------
                                    248 ;	 function TIM1_CAP_COM_IRQHandler
                                    249 ;	-----------------------------------------
                                    250 ;	Register assignment is optimal.
                                    251 ;	Stack space usage: 0 bytes.
      00832D                        252 _TIM1_CAP_COM_IRQHandler:
                                    253 ;	./src/stm8s_it.c: 241: }
                                    254 ; genLabel
      00832D                        255 00101$:
                                    256 ; genEndFunction
      00832D 80               [11]  257 	iret
                                    258 ;	./src/stm8s_it.c: 273: INTERRUPT_HANDLER(TIM2_UPD_OVF_BRK_IRQHandler, 13)
                                    259 ; genLabel
                                    260 ;	-----------------------------------------
                                    261 ;	 function TIM2_UPD_OVF_BRK_IRQHandler
                                    262 ;	-----------------------------------------
                                    263 ;	Register assignment is optimal.
                                    264 ;	Stack space usage: 0 bytes.
      00832E                        265 _TIM2_UPD_OVF_BRK_IRQHandler:
                                    266 ;	Reset bit 6 of reg CC. Hardware bug workaround.
      00832E 62               [ 2]  267 	div	x, a
                                    268 ;	./src/stm8s_it.c: 275: TIM2_ClearFlag(TIM2_FLAG_UPDATE);
                                    269 ; genSend
      00832F 5F               [ 1]  270 	clrw	x
      008330 5C               [ 1]  271 	incw	x
                                    272 ; genCall
      008331 CD 86 53         [ 4]  273 	call	_TIM2_ClearFlag
                                    274 ;	./src/stm8s_it.c: 276: svujcas++;
                                    275 ; genPlus
      008334 CE 00 03         [ 2]  276 	ldw	x, _svujcas+2
      008337 1C 00 01         [ 2]  277 	addw	x, #0x0001
      00833A 90 CE 00 01      [ 2]  278 	ldw	y, _svujcas+0
      00833E 24 02            [ 1]  279 	jrnc	00103$
      008340 90 5C            [ 1]  280 	incw	y
      008342                        281 00103$:
                                    282 ; genAssign
      008342 CF 00 03         [ 2]  283 	ldw	_svujcas+2, x
      008345 90 CF 00 01      [ 2]  284 	ldw	_svujcas+0, y
                                    285 ; genLabel
      008349                        286 00101$:
                                    287 ;	./src/stm8s_it.c: 277: }
                                    288 ; genEndFunction
      008349 80               [11]  289 	iret
                                    290 ;	./src/stm8s_it.c: 284: INTERRUPT_HANDLER(TIM2_CAP_COM_IRQHandler, 14)
                                    291 ; genLabel
                                    292 ;	-----------------------------------------
                                    293 ;	 function TIM2_CAP_COM_IRQHandler
                                    294 ;	-----------------------------------------
                                    295 ;	Register assignment is optimal.
                                    296 ;	Stack space usage: 0 bytes.
      00834A                        297 _TIM2_CAP_COM_IRQHandler:
                                    298 ;	./src/stm8s_it.c: 289: }
                                    299 ; genLabel
      00834A                        300 00101$:
                                    301 ; genEndFunction
      00834A 80               [11]  302 	iret
                                    303 ;	./src/stm8s_it.c: 299: INTERRUPT_HANDLER(TIM3_UPD_OVF_BRK_IRQHandler, 15)
                                    304 ; genLabel
                                    305 ;	-----------------------------------------
                                    306 ;	 function TIM3_UPD_OVF_BRK_IRQHandler
                                    307 ;	-----------------------------------------
                                    308 ;	Register assignment is optimal.
                                    309 ;	Stack space usage: 0 bytes.
      00834B                        310 _TIM3_UPD_OVF_BRK_IRQHandler:
                                    311 ;	./src/stm8s_it.c: 304: }
                                    312 ; genLabel
      00834B                        313 00101$:
                                    314 ; genEndFunction
      00834B 80               [11]  315 	iret
                                    316 ;	./src/stm8s_it.c: 311: INTERRUPT_HANDLER(TIM3_CAP_COM_IRQHandler, 16)
                                    317 ; genLabel
                                    318 ;	-----------------------------------------
                                    319 ;	 function TIM3_CAP_COM_IRQHandler
                                    320 ;	-----------------------------------------
                                    321 ;	Register assignment is optimal.
                                    322 ;	Stack space usage: 0 bytes.
      00834C                        323 _TIM3_CAP_COM_IRQHandler:
                                    324 ;	./src/stm8s_it.c: 316: }
                                    325 ; genLabel
      00834C                        326 00101$:
                                    327 ; genEndFunction
      00834C 80               [11]  328 	iret
                                    329 ;	./src/stm8s_it.c: 326: INTERRUPT_HANDLER(UART1_TX_IRQHandler, 17)
                                    330 ; genLabel
                                    331 ;	-----------------------------------------
                                    332 ;	 function UART1_TX_IRQHandler
                                    333 ;	-----------------------------------------
                                    334 ;	Register assignment is optimal.
                                    335 ;	Stack space usage: 0 bytes.
      00834D                        336 _UART1_TX_IRQHandler:
                                    337 ;	./src/stm8s_it.c: 331: }
                                    338 ; genLabel
      00834D                        339 00101$:
                                    340 ; genEndFunction
      00834D 80               [11]  341 	iret
                                    342 ;	./src/stm8s_it.c: 338: INTERRUPT_HANDLER(UART1_RX_IRQHandler, 18)
                                    343 ; genLabel
                                    344 ;	-----------------------------------------
                                    345 ;	 function UART1_RX_IRQHandler
                                    346 ;	-----------------------------------------
                                    347 ;	Register assignment is optimal.
                                    348 ;	Stack space usage: 0 bytes.
      00834E                        349 _UART1_RX_IRQHandler:
                                    350 ;	./src/stm8s_it.c: 343: }
                                    351 ; genLabel
      00834E                        352 00101$:
                                    353 ; genEndFunction
      00834E 80               [11]  354 	iret
                                    355 ;	./src/stm8s_it.c: 351: INTERRUPT_HANDLER(I2C_IRQHandler, 19)
                                    356 ; genLabel
                                    357 ;	-----------------------------------------
                                    358 ;	 function I2C_IRQHandler
                                    359 ;	-----------------------------------------
                                    360 ;	Register assignment is optimal.
                                    361 ;	Stack space usage: 0 bytes.
      00834F                        362 _I2C_IRQHandler:
                                    363 ;	./src/stm8s_it.c: 356: }
                                    364 ; genLabel
      00834F                        365 00101$:
                                    366 ; genEndFunction
      00834F 80               [11]  367 	iret
                                    368 ;	./src/stm8s_it.c: 390: INTERRUPT_HANDLER(UART3_TX_IRQHandler, 20)
                                    369 ; genLabel
                                    370 ;	-----------------------------------------
                                    371 ;	 function UART3_TX_IRQHandler
                                    372 ;	-----------------------------------------
                                    373 ;	Register assignment is optimal.
                                    374 ;	Stack space usage: 0 bytes.
      008350                        375 _UART3_TX_IRQHandler:
                                    376 ;	./src/stm8s_it.c: 395: }
                                    377 ; genLabel
      008350                        378 00101$:
                                    379 ; genEndFunction
      008350 80               [11]  380 	iret
                                    381 ;	./src/stm8s_it.c: 402: INTERRUPT_HANDLER(UART3_RX_IRQHandler, 21)
                                    382 ; genLabel
                                    383 ;	-----------------------------------------
                                    384 ;	 function UART3_RX_IRQHandler
                                    385 ;	-----------------------------------------
                                    386 ;	Register assignment is optimal.
                                    387 ;	Stack space usage: 0 bytes.
      008351                        388 _UART3_RX_IRQHandler:
                                    389 ;	./src/stm8s_it.c: 407: }
                                    390 ; genLabel
      008351                        391 00101$:
                                    392 ; genEndFunction
      008351 80               [11]  393 	iret
                                    394 ;	./src/stm8s_it.c: 416: INTERRUPT_HANDLER(ADC2_IRQHandler, 22)
                                    395 ; genLabel
                                    396 ;	-----------------------------------------
                                    397 ;	 function ADC2_IRQHandler
                                    398 ;	-----------------------------------------
                                    399 ;	Register assignment is optimal.
                                    400 ;	Stack space usage: 0 bytes.
      008352                        401 _ADC2_IRQHandler:
                                    402 ;	./src/stm8s_it.c: 422: return;
                                    403 ; genReturn
                                    404 ; genLabel
      008352                        405 00101$:
                                    406 ;	./src/stm8s_it.c: 424: }
                                    407 ; genEndFunction
      008352 80               [11]  408 	iret
                                    409 ;	./src/stm8s_it.c: 473: INTERRUPT_HANDLER(TIM4_UPD_OVF_IRQHandler, 23)
                                    410 ; genLabel
                                    411 ;	-----------------------------------------
                                    412 ;	 function TIM4_UPD_OVF_IRQHandler
                                    413 ;	-----------------------------------------
                                    414 ;	Register assignment might be sub-optimal.
                                    415 ;	Stack space usage: 0 bytes.
      008353                        416 _TIM4_UPD_OVF_IRQHandler:
                                    417 ;	Reset bit 6 of reg CC. Hardware bug workaround.
      008353 62               [ 2]  418 	div	x, a
                                    419 ;	./src/stm8s_it.c: 475: TIM4_ClearFlag(TIM4_FLAG_UPDATE);
                                    420 ; genSend
      008354 A6 01            [ 1]  421 	ld	a, #0x01
                                    422 ; genCall
      008356 CD 86 D9         [ 4]  423 	call	_TIM4_ClearFlag
                                    424 ;	./src/stm8s_it.c: 476: miliseconds++;
                                    425 ; genAssign
      008359 CE 00 07         [ 2]  426 	ldw	x, _miliseconds+2
      00835C 90 CE 00 05      [ 2]  427 	ldw	y, _miliseconds+0
                                    428 ; genPlus
      008360 5C               [ 1]  429 	incw	x
      008361 26 02            [ 1]  430 	jrne	00103$
      008363 90 5C            [ 1]  431 	incw	y
      008365                        432 00103$:
                                    433 ; genAssign
      008365 CF 00 07         [ 2]  434 	ldw	_miliseconds+2, x
      008368 90 CF 00 05      [ 2]  435 	ldw	_miliseconds+0, y
                                    436 ; genLabel
      00836C                        437 00101$:
                                    438 ;	./src/stm8s_it.c: 477: }
                                    439 ; genEndFunction
      00836C 80               [11]  440 	iret
                                    441 ;	./src/stm8s_it.c: 485: INTERRUPT_HANDLER(EEPROM_EEC_IRQHandler, 24)
                                    442 ; genLabel
                                    443 ;	-----------------------------------------
                                    444 ;	 function EEPROM_EEC_IRQHandler
                                    445 ;	-----------------------------------------
                                    446 ;	Register assignment is optimal.
                                    447 ;	Stack space usage: 0 bytes.
      00836D                        448 _EEPROM_EEC_IRQHandler:
                                    449 ;	./src/stm8s_it.c: 490: }
                                    450 ; genLabel
      00836D                        451 00101$:
                                    452 ; genEndFunction
      00836D 80               [11]  453 	iret
                                    454 	.area CODE
                                    455 	.area CONST
                                    456 	.area INITIALIZER
                                    457 	.area CABS (ABS)
