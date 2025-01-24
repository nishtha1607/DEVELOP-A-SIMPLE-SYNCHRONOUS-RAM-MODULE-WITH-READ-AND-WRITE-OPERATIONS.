// Testbench for the Synchronous RAM Module
module tb_ram();
    parameter ADDR_WIDTH = 4;
    parameter DATA_WIDTH = 8;

    reg clk;
    reg we;
    reg [ADDR_WIDTH-1:0] addr;
    reg [DATA_WIDTH-1:0] data_in;
    wire [DATA_WIDTH-1:0] data_out;

    // Instantiate the RAM module
    ram #(ADDR_WIDTH, DATA_WIDTH) dut (
        .clk(clk),
        .we(we),
        .addr(addr),
        .data_in(data_in),
        .data_out(data_out)
    );

    // Clock generation
    initial begin
        clk = 0;
        forever #5 clk = ~clk; // 10ns clock period
    end

    // Testbench logic
    initial begin
        // Initialize inputs
        we = 0;
        addr = 0;
        data_in = 0;

        // Test write operation
        #10;
        we = 1;
        addr = 4'b0010;
        data_in = 8'hAA; // Write 0xAA to address 2
        #10;

        we = 1;
        addr = 4'b0100;
        data_in = 8'h55; // Write 0x55 to address 4
        #10;

        // Test read operation
        we = 0;
        addr = 4'b0010; // Read from address 2
        #10;

        addr = 4'b0100; // Read from address 4
        #10;

        // Finish simulation
        $stop;
    end

    // Monitor output
    initial begin
        $monitor($time, " WE=%b Addr=%h Data_in=%h Data_out=%h", we, addr, data_in, data_out);
    end

    initial begin
        $dumpfile("dump.vcd");
        $dumpvars(0);
    end

endmodule