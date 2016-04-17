+++
author = "Prasad Pandit"
categories = ["VHDL","FPGA"]
date = "2016-04-17T03:25:46-07:00"
description = "How to Blink and LED using FPGA"
featured = ""
featuredalt = ""
featuredpath = "date"
linktitle = ""
title = "Simple Clock Divider using VHDL"
type = "post"

+++
When I started working with VHDL and FPGAs, the first ever project that came to my mind was blinking an LED. But since we all know that most of the development boards have high frequency clocks from around 20MHz to as high you can get. So if we directly connect that clock to LED the blink rate will be so high that it will not be visible to our naked eye.

To blink an LED the simplest method is dividing a clock. I have used a simple counter which counts up to certain maximum value and flips the output signal.  For this project I am using `Altera DE-1 board`. Following is the logic to blink an LED.

This is a clock divider code, just set the max-count value as per your requirenment.

For ex. If I want 1Hz freq. set the max count to i/p freq value viz.
1sec = 1Hz

Then, to get time period of 1sec i.e. 1 Hz frequency set max-count to 240000 as shown below:

`1sec  =  24000000  -- for i/p frequency of 24 MHz`

To get your desired frequency just calculate the maxcount with the formula given below:

`max_count = 24000000 * (1/your required frequency)`

## Code:

```
 library IEEE;

 use IEEE.STD_LOGIC_1164.ALL;
 use IEEE.numeric_std.all;

 entity clk_div is
    Port (
          Clk   : in std_logic;
          rst   : in std_logic;
          op    : out std_logic
    );
 end clk_div;


 architecture behavioral of clk_div is

    constant max_count : natural := 24000000;

 begin

  process(Clk,rst)
        variable count : natural range 0 to max_count;

    begin
        if rst = '0' then
            count := 0;
            op    <= '1';
        elsif rising_edge(Clk) then
            if count < (max_count/2)-1 then
                op    <='1';
                count := count + 1;
            elsif count < max_count-1 then
                op    <='0';
                count := count + 1;
            else
                count := 0;
                op    <='1';
            end if;
     end if;

  end process;

 end behavioral;

```
