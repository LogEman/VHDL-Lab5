| X | Y | Z | B | O | MATCH |
| :---- | :---- | :---- | :---- | :---- | :---- |
| 0 | 0 | 0 | 0 | 0 | X |
| 0 | 0 | 0 | 1 | 0 | X |
| 0 | 0 | 1 | 0 | 0 | X |
| 0 | 0 | 1 | 1 | 0 | X |
| 0 | 1 | 0 | 0 | 0 | X |
| 0 | 1 | 0 | 1 | 0 | X |
| 0 | 1 | 1 | 0 | 0 | X |
| 0 | 1 | 1 | 1 | 1 | X |
| 1 | 0 | 0 | 0 | 0 | X |
| 1 | 0 | 0 | 1 | 0 | X |
| 1 | 0 | 1 | 0 | 0 | X |
| 1 | 0 | 1 | 1 | 1 | X |
| 1 | 1 | 0 | 0 | 1 | X |
| 1 | 1 | 0 | 1 | 1 | X |
| 1 | 1 | 1 | 0 | 1 | X |
| 1 | 1 | 1 | 1 | 1 | X |

For O = XY + XZB + YZB  
**Inputs**: X, Y, Z, B  
**Output**: O  
**Match**: Tested on hardware and matches table    

Running **Should** be as simple as downloading folder(as zip **using the giant green code button**), extracting, and running "lab5.xpr" (Vivado Project File). Code can be seen directly in .srcs

## Design Sources Code
**Path**: lab5_github/lab5.srcs/sources_1/new/lab_5.vhd

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity lab_5 is
    Port ( X : in STD_LOGIC;
           Y : in STD_LOGIC;
           Z : in STD_LOGIC;
           B : in STD_LOGIC;
           O : out STD_LOGIC);
end lab_5;

architecture Behavioral of lab_5 is

begin

    O <= (X AND Y) or (X AND Z AND B) or (Y AND Z AND B);

end Behavioral;
```

## Constraints Code
**Path**: lab5_github/lab5.srcs/constrs_1/new/lab_5.xdc

```tcl
## Switches
set_property PACKAGE_PIN V17 [get_ports {X}]					
	set_property IOSTANDARD LVCMOS33 [get_ports {X}]
set_property PACKAGE_PIN V16 [get_ports {Y}]					
	set_property IOSTANDARD LVCMOS33 [get_ports {Y}]
set_property PACKAGE_PIN W16 [get_ports {Z}]					
	set_property IOSTANDARD LVCMOS33 [get_ports {Z}]
set_property PACKAGE_PIN W17 [get_ports {B}]					
	set_property IOSTANDARD LVCMOS33 [get_ports {B}]
	
## LEDs
set_property PACKAGE_PIN U16 [get_ports {O}]					
    set_property IOSTANDARD LVCMOS33 [get_ports {O}]
```
