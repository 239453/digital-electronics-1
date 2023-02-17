# Lab 2: INSERT_YOUR_FIRSTNAME INSERT_YOUR_LASTNAMEE

### 2-bit comparator

1. Karnaugh maps for other two functions of 2-bit comparator:

   Greater than:

   ![326762024_1584147788771081_5327417287824819294_n](https://user-images.githubusercontent.com/124879406/219625787-9d7288da-e441-4784-b051-1882dddc7316.png)

   Less than:

  ![less](https://user-images.githubusercontent.com/124879406/219625128-f99c8de0-f874-46da-8d1b-8a6e2febb9af.png)



2. Mark the largest possible implicants in the K-map and according to them, write the equations of simplified SoP (Sum of the Products) form of the "greater than" function and simplified PoS (Product of the Sums) form of the "less than" function.

  ![331011455_501148555518614_8590612439944978352_n](https://user-images.githubusercontent.com/124879406/219633800-015ba6f9-9efc-454a-9fe5-93262da7c587.jpg)
![331190357_1419781615431133_6697114378392123135_n](https://user-images.githubusercontent.com/124879406/219634010-4c56c382-1659-4a50-b902-766b4d6b835d.jpg)

### 4-bit comparator

1. Listing of VHDL stimulus process from testbench file (`testbench.vhd`) with at least one assert (use BCD codes of your student ID digits as input combinations). Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   Last two digits of my student ID: **xxxx??**

```vhdl
    p_stimulus : process
    begin
        -- Report a note at the beginning of stimulus process
        report "Stimulus process started";

        -- First test case ...
        --last two numpbers of my is are 5,3 that mean "0101" and "0011"
        s_b <= "0011"; s_a <= "0101"; wait for 100 ns;
        -- ... and its expected outputs
        assert (( s_B_greater_A = '0') and
                ( s_B_equals_A  = '0') and
                (s_B_less_A    = '1'))
        -- If true, then do not report anything
        -- If false, then report the following error
        report "Input combination b=0, a=0 FAILED" severity error;


        s_b <= "0000"; s_a <= "1111"; wait for 100 ns;
         assert (( s_B_greater_A = '0') and
                ( s_B_equals_A  = '0') and
                (s_B_less_A    = '0'))
                report "Input combination b=0000, a=1111 FAILED" severity error;
        
        s_b <= "1111"; s_a <= "0000"; wait for 100 ns;
         assert (( s_B_greater_A = '1') and
                ( s_B_equals_A  = '0') and
                (s_B_less_A    = '0'))
       report "Input combination b=1111, a=0000 FAILED" severity error;
        -- WRITE OTHER TEST CASES HERE


        -- Report a note at the end of stimulus process
        report "Stimulus process finished";
        wait; -- Data generation process is suspended forever
    end process p_stimulus;
```

2. Link to your public EDA Playground example:

   https://www.edaplayground.com/x/rNFZ
