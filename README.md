//文件的打开和关闭
//文件在读写之前应该先打开文件，在使用结束之后应该关闭文件
//在编写文件的时候，在打开文件的同时，都会返回一个FILE*的指针变量指向该文件，相当于建立了指针和文件的关系
//fopen打开文件，fclose关闭文件
#include<stdio.h>
#include<string.h>
#include<strno.h>
 int main()
{
      //打开文件test.txt（相对路径）
      //..表上一个路径
      //.表当前路径
      //fopen（"../test.txt","r");
      //路径分为绝对路径和相对路径，绝对路径将文件所有的路径用\\连接列出来
      //fopen(" 文件名“，”模式“）
      FILE* pf=fopen("test.txt","r");//以r形式打开文件若没有文件则显示不存在，若以w的形式打开文件，文件不存在则新创建一个文件
      if(pf==NULL;)
      {
            printf("%s\n",strerror(errno));
      }
      //打开成功
      //读文件
      //关闭文件
      fclose(pf);
      pf=NULL;
 return 0；     
 }
 
 
 int main()
 {
      FILE* pfWrite=fopen("TEST.txt","w");
      if(pfWrite==NULL)
      {
            printf("%s\n",strerror(errno));
            return 0;
      }
      //写文件
      fputc('b',pfWrite);
      fputc('i',pfWrite);
      fputc('t',pfWrite);
      //关闭文件
      fclose(pfWrite);
      pfWrite=NULL;
      return 0;
 }
 
 //读文件
  int main()
 {
      FILE* pfRead=fopen("TEST.txt","r");
      if(pfRead==NULL)
      {
            printf("%s\n",strerror(errno));
            return 0;
      }
      //读文件
      printf("%c",fgetc(pfRead));
      printf("%c",fgetc(pfRead));
      printf("%c",fgetc(pfRead));
      //关闭文件
      fclose(pfRead);
      pfRead=NULL;
      return 0;
 }
 
 
 
 //从键盘输入
 //输出到屏幕
 //键盘&屏幕都是外部设备
 //键盘-标准输入设备-stdin
 //屏幕-标准输出设备-stdout
 //是一个程序默认打开的两个流设备，分别为stdin；stdout；stderr，类型都是FILE*
 
 
 int main()
 {
      int ch=fgetc(stdin);
      fputc(ch,stdout);
      return  0;
 }
 
 
 
