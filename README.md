# CD4511-en-Verilog
## Con Latch, decodificador de bcd a 7seg y Multiplexor con salida de un bus de 8 Bits conectadas a un display de 7seg


### Implementacion en verilog



| LE| ~BI | ~LT | G |
| ----- | ---- | ---- | ---- |
| 0 | 0 | 0 | DECO |
| 0 | 0 | 1 | LT |
| 0 | 1 | 0 | x2 = 0 |
| 0 | 1 | 1 | LT |
| 1 | 0 | 0 | LATCH |
| 1 | 0 | 1 | LT |
| 1 | 1 | 0 | x6 = 0 |
| 1 | 1 | 1 | LT |

```
		
		//bloque de codigo...
		
		```
