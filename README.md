# Digital IC Design

## Approximate Average

### Introduction
- Please design a computational system whose transfer function is defined as follow. A series of 8-bit positive integer is generated as the input of the computational system by the test bench. The output value Y is a 10-bit positive integer, which is calculated according to equations (1), (2), (3) and (4).
![pic](img/pic.jpg)
- The computational system produces the output sequence according to the given input sequence. Each input and output data in the respective sequence is indexed. This index, in terms of hardware, is the relative time when the input data is given or the output data is ready. Thinking as a hardware designer, the approximate average is chosen from the last *n* input data which should be stored in the system. The system should be able to calculate the integral part of the real average of the last *n* input data first. And then if the integral part of the real average equals to any one of the last *n* input data, the approximate average is simply the integral part. Else the approximate average is the one which is one of the last *n* input data whose value is smaller than and closest to the integral part of the real average. The above descriptions stated the desired operations as those defined by equations (1), (2), and (3).
- After the approximate average is obtained, the output value can be calculated according to equation (4). First, the last *n* input value is added by the corresponding approximate average. And then they are summed up and divided by *n-1*. The output value is the quotient after division.
- For example, assume that n=4, X1=3, X2=24, X3=16, X4=8, and X5=3. After the first 5 input items are given, the system should store them and calculate the output value. The average of the first 4 input values is 12(only the integral part is left). Since it is not in the set of {X1, X2, X3, X4}, the system selects one from {X1, X2, X3, X4} as the approximate average whose value is smaller than 12 and close to 12. In this case, the approximate average is 8. So the first output value is calculated n as [[(3 + 8) + (24 + 8) + (16 + 8) + (8 + 8)] /[(4 - 1)]] = 27 . Similar to those described above, when the 5th input data item is given, the system should store X2, X3, X4 and X5 and calculate the corresponding output value. The 2nd output value should be the same as the first one because the values stored in the system is the same.

## AUTHORS
[Yu-Tong Shen](https://github.com/yutongshen/)
