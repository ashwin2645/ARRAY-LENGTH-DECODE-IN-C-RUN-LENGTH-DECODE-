# ARRAY-LENGTH-DECODE-IN-C-RUN-LENGTH-DECODE-
/*

sample input1 = a12b5c3a

            output1 = aaaaaaaaaaaabbbbbccca

sample input2 = A5Bc3D1

        output2 = AAAAABCCCD

*/

 #include<stdio.h> 

#include<string.h>

int main()

{

    char str[50];

    scanf("%s",str);//getting input

    int count=0,i,m,k;

    int n=strlen(str);

    for(i=0;i<n;i++)

    {

        m=0,k=0;

        count=0;

        if(str[i]>='a'&&str[i]<='z'|| str[i]>='A'&& str[i]<='Z')    //checking the current index is character or not

        {

            if(str[i+1]>='0'&&str[i+1]<='9')//checking character next index is number or not

            {

                if(str[i+2]>='0'&&str[i+2]<='9')//checking character decoding value is double digit or not

                {

                      m=str[i+1]-'0';

                      m=m*10;

                      k=str[i+2]-'0';

                      count=m+k;

                     

                }

                else

                count=str[i+1]-'0';

            }

            if(count==0)

            {

                printf("%c",str[i]);

            }

            while(count--)

            printf("%c",str[i]);

        }

    }

}
