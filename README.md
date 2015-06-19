#include<stdio.h>
#include<conio.h>
#include<dir.h>
#include<string.h>
int main()
{
 int   d,tcount=0,mcount=0,ncount=0,pcount=0,bcount=0,ccount=0,count=0,ecount=0;
 int gcount=0,rcount=0,kcount=0,scount=0;
 char *p;
 struct ffblk a;    //to print files status
 clrscr();
 printf("press any key to view the files in the current directory\n");
 getch();
 d=findfirst("*.*",&a,0);    //("*.c/*",struct ffblk *ffblk,int attri)
 while(!d)
 {
  printf("%s\t",a.ff_name);//(struct ffblk *ffblk)
  printf("%ld\n",a.ff_fsize);//print the size of file
  p=strchr(a.ff_name,'.'); //search the first occurrence of the character before'.'
  if(p&&*(p+1))   //search second character
{
if(strcmp((p+1),"TXT")==0)   //if string compare of 2nd char equalto 'txt'
tcount=tcount+1;         //then tcount++
else if(strcmp((p+1),"MP3")==0) //if string compare of 2nd char equalto 'mp3'
mcount=mcount+1;          //then mcount++
else if(strcmp((p+1),"MP4")==0)
ncount=ncount+1;
else if(strcmp((p+1),"PDF")==0)
pcount=pcount+1;
else if(strcmp((p+1),"COM")==0)
ccount=ccount+1;
else if(strcmp((p+1),"BAK")==0)
bcount=bcount+1;
else if(strcmp((p+1),"C")==0)
count=count+1;
else if(strcmp((p+1),"EXE")==0)
ecount=ecount+1;
else if(strcmp((p+1),"CFG")==0)
gcount=gcount+1;
else if(strcmp((p+1),"DPR")==0)
rcount=rcount+1;
else if(strcmp((p+1),"DSK")==0)
kcount=kcount+1;
else if(strcmp((p+1),"SWP")==0)
scount=scount+1;

 }
  d=findnext(&a); //used to find the directory for the list of files
 }
 printf("the count of TEXT files are %d\n",tcount);//display text file count value
 printf("the count of MP3 files are %d\n",mcount);
 printf("the count of MP4 files are %d\n",ncount);
 printf("the count of PDF files are %d\n",pcount);
 printf("the count of BAK files are %d\n",bcount);
 printf("the count of COM files are %d\n",ccount);
 printf("the count of C files are %d\n",count);
 printf("the count of EXE files are %d\n",ecount);
 printf("the count of CFG files are %d\n",gcount);
 printf("the count of DPR files are %d\n",rcount);
 printf("the count of DSK files are %d\n",kcount);
 printf("the count of SWP files are %d\n",scount);
 getch();
 return 0;
}


