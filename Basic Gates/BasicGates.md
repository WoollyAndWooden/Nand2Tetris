
# My implementations

Below are my implementations for each of the gates required by the course

## Logic Gates

1. Not
    ``

        CHIP Not {
            IN in;
            OUT out;
            PARTS:
            Nand(a = in, b = in, out = out);
        }
    ``

2. And
    ``

        CHIP And {
            IN a, b;
            OUT out;
            
            PARTS:
            Nand(a=a, b=b, out=L1);
            Nand(a=L1, b=L1, out=out); 
        }
    ``

3. Or
    ``
    
        CHIP Or {
            IN a, b;
            OUT out;

            PARTS:
            Nand(a=a, b=a, out=notA);
            Nand(a=b, b=b, out=notB);
            Nand(a=notA, b=notB, out=out);
        }
    ``

4. Xor
    ``
    
        CHIP Xor {
            IN a, b;
            OUT out;

            PARTS:
            Nand(a=a, b=b, out=L1Nand);
            Nand(a=a, b=L1Nand, out=L2NandA);
            Nand(a=L1Nand, b=b, out=L2NandB);
            Nand(a=L2NandA, b=L2NandB, out=out);
        }
    ``
