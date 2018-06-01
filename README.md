# jsencryption


1. 字符串 每个数字或者字母之间加固定n个参数   进行加密  解密 真好相反
 for (i = 0; i < 15; i++)
  {
key=itemInsert(key,n个参数,i + j);
      j += n;
  }
 2. 解密
 for (i = 1; i < 15; i++)
  {
key=itemRemove(key,n个参数,i);
  }
  最后一个
  itemRemove(key,n个参数,length)
