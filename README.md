# Urban-ergodic-problem

Urban ergodic problem

	给出六个城市的道路连接图,找出从某一城市出发,遍历每个城市一次且仅一次的最短路径及其路程长度.
  
  
【参考程序】

const

     a:array[1..6,1..6]of 0..10  {城市间连接图.数字表示两城市间的路程}
     
       =((0,4,8,0,0,0),
       
         (4,0,3,4,6,0),
         
         (8,3,0,2,2,0),
         
         (0,4,2,0,4,9),
         
         (0,6,2,4,0,4),
         
         
         (0,0,0,9,4,0));
         
var

   had:array[1..6]of boolean;              {某个城市是否已到过}
   
   pathmin,path:array[1..6]of integer;     {记录遍历顺序}
   
   ii,first,i,summin,total:integer;
   
procedure output(dep:integer); sum,i,j:integer;

     sum:=0; i:=2 6    {求这条路的路程总长}
     
     if sum><6 then find(dep+1)
     
     
                     else output(dep);
                     
            had[i]:=false;        {回溯}
            
            path[dep]:=0;
            
         end;
         
end;

begin

   for first:=1 to 6 do begin        {轮流从每一个城市出发,寻找各自的最短路}
   
     fillchar(had,sizeof(had),false);
     
     fillchar(path,sizeof(path),0);
     
     total:=0;
     
     SumMin:=maxint;                {最短路程}
     
     path[1]:=first;had[first]:=true;{处理出发点的城市信息,记录在册并置到过标志}
     
     find(2);                        {到下一城市}
     
     writeln('from city ',first,' start,total is:',total,'  the min sum:',summin);
     
     for i:=1 to 6 do write(PathMin[i]);writeln; {输出某个城市出发的最短方案}
     
   end;
   
end.
