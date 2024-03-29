# Lab 7: INSERT_YOUR_FIRSTNAME INSERT_YOUR_LASTNAME

### Display driver

1. Listing of VHDL code of the completed process `p_mux`. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

```vhdl
        --------------------------------------------------------
    -- p_mux:
    -- A sequential process that implements a multiplexer for
    -- selecting data for a single digit, a decimal point 
    -- signal, and switches the common anodes of each display.
    --------------------------------------------------------
    p_mux : process(clk)
    begin
        if rising_edge(clk) then
            if (reset = '1') then
                s_hex <= data0_i;
                dp_o  <= dp_i(0);
                dig_o <= "1110";
            else
                case sig_cnt_2bit is

          when "11" =>
            sig_hex <= data3;
            dp      <= dp_vect(3);
            dig     <= "0111";

          when "10" =>
            -- DEFINE ALL OUTPUTS FOR "10" HERE
            sig_hex <= data2;
            dp      <= dp_vect(2);
            dig     <= "1011";

          when "01" =>
            -- DEFINE ALL OUTPUTS FOR "01" HERE
             sig_hex <= data1;
            dp      <= dp_vect(1);
            dig     <= "1101";
          when others =>
            -- DEFINE ALL OUTPUTS FOR "00" HERE
            sig_hex <= data0;
            dp      <= dp_vect(0);
            dig     <= "1110";
        end case;
            end if;
        end if;
    end process p_mux;
```

### Eight-digit driver

1. Image of the 8-digit driver's block schematic. The image can be drawn on a computer or by hand. Always name all inputs, outputs, components, and internal signals!

   ![IMG_20230327_140041](https://user-images.githubusercontent.com/124675843/227936029-8f90caed-0ef9-42ae-bdbe-5cc7b36dadf7.jpg)

