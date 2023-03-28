# FPGA-Based-Design-System

//HALF ADDER PROGRAM
module halfadd(hsum,hcarry,ha,hb);
output hsum,hcarry;
input ha,hb;
assign hsum = ha ^ hb;
assign hcarry = ha & hb;
endmodule


//HALF ADDER PROGRAM TESTBENCH
module halfadd_tb;
reg a, b;
wire sum, cout;
initial
$monitor ("ab = %b, sum = %b, cout = %b", {a, b}, sum, cout);
initial //apply input vectors
begin
#0 a=1'b0; b=1'b0;
#10 a=1'b0; b=1'b1;
#10 a=1'b1; b=1'b0;
#10 a=1'b1; b=1'b1;
#10 $stop;
end
//instantiate the module into the test bench
halfadd inst1 (
.ha(a),
.hb(b),
.hsum(sum),
.hcarry(cout)
);
endmodule
