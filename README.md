# Caesar-Cipher
This is my first project in there and I hope it will help someone.
/*
e.g. enter text to encrypt: Do not go gentle into that good night, Old age should burn and rave at close of day; Rage, rage against the dying of the light. Do not go gentle into that good night.
	key=2
	output: Fq pqv igpvng kpvq vjcv iqqf pkijv, Qnf cig ujqwnf dwtp cpf tcxg cv enqug qh fca; Tcig, tcig cickpuv vgj fakpi qh vjg nkijv. Fq pqv iq igpvng kpvq vjcv iqqf pkijv.
*/

#include <stdio.h>
#include <string.h>
#include <conio.h>
int main()
{	
	int i=0,key;
	char n[1000];
	printf("enter text to encrypt:\n");
	gets(n);
	printf("enter the key:\n");
	scanf("%d",&key);
	
	while(n[i]!='\0')
  	{
		if(!((n[i]>=0&&n[i]<65)||(n[i]>90&&n[i]<97)||(n[i]>122&&n[i]<=127)))
 			{
				int a=0;
				a+=(96<n[i]<123?((n[i]-97+key)%26+97):((n[i]-65+key)%26+65));
				
				if(n[i]>='A'&&n[i]<='Z' && a>90)
				{
					a-=90;
					a+=64;
				}
				
				printf("%c",a);
 			}
 		else
 			{
 				printf("%c",n[i]);
 			}
	i++;
	}
}
