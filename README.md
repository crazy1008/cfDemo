﻿词法分析，简而来说就是对字符序列转化为单词的过程。在开始写程序时，首先得分析每个过程，每种情况，必须做到心中有数。在进行代码调试出错要能知道哪里出错，这样才能高效完成代码编程。
* 首先第一步把单词定义表做下分类：
    *  关键字和非关键字
    *  整数
    *  字母
    *  终结符
* 第二步对从txt文档中的内容（这里我是一行一行的读）进行分析：
    * 注释（//，/**/）
    * 空字符串
    * 由空格组成的字符串
    * 字符串
* 第三步主要对第二步的内容进行进行分析
  * 遇到注释就对注释行保留，进而读取下一行
  * 遇到空字串直接退出，进而读取下一行
  * 遇到空格组成的字符串记录该行，进而读取下一行
  * 遇到字符串，首先从第一个字符开始进行判断：
    1. 如果是终结符，就判断下一位如果可以和上一位组成特定的单词就输出它们的组合，如果下位不能和上一位组成特单词就单独输出。
    2. 如果是字母，每次都判断下一位是否是终结符，直到遇到终结符，就可以判断从上一个终结符到下一个终结之间组成的单词，（空格除外）如果单词的第一个字符为数字，那么就判断该单词是error,如果不是就判断是否为关键字或者非关键字
    3. 如果是数字，每次都判断下一位是否为终结符，知道遇到终结符，就可以判断从上一个终结到下一个终结符之间组成的单词是不是整数。
    4. 如果是空格，那么终结符就向下一位移动

