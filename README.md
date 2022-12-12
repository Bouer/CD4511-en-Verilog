# CD4511-en-Verilog
## Con Latch, decodificador de bcd a 7seg y Multiplexor con salida de un bus de 8 Bits conectadas a un display de 7seg

![GRAFICO CD4511](https://user-images.githubusercontent.com/70662198/207092923-a8efa512-5232-4e44-93aa-aab63915a20a.jpg)



Tabla de verdad del CD4511


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






### Implementacion en verilog
```
		
module CD4511;

    reg [0:4] a;
    //input [0:7] f,
    reg LE;
    reg LT;
    reg BI;
    //input [0:7] y,
	 wire [0:7] S;
	 wire [0:7] DecoLatch;
	 wire [0:7] LatchPlexor;
	 
	 
	deco u1(
	 .A(a),
	 .f(DecoLatch)
	);
	

	latch u2(
	 .F(DecoLatch),
	 .LE(LE),
	 .y(LatchPlexor)
	);
	
	plexor u3(
	 .G(DecoLatch),
	 .Y(LatchPlexor),
	 .LT(LT), 
	 .LE(LE),
	 .BI(BI),
	 .S(S)
	);
	
	initial begin
		// Initialize Inputs
	LE = 0;   LT = 0;   BI = 0;	a  = 4; 	#200;
	LE = 0;   LT = 0;   BI = 1;	a  = 4;	#200;
	LE = 0;   LT = 1;   BI = 0;	a  = 4;	#200;
	LE = 0;   LT = 1;   BI = 1;	a  = 4;	#100;
	LE = 1;   LT = 0;   BI = 0;	a  = 4;	#200;
	LE = 1;   LT = 0;   BI = 1;	a  = 4;	#200;
	LE = 1;   LT = 1;   BI = 0;	a  = 5;	#200;
	LE = 1;   LT = 1;   BI = 1;	a  = 5;	#200;
	
	end
	
endmodule
		
```






