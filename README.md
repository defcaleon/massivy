# massivy
program laba4;

{$APPTYPE CONSOLE}

{$R *.res}

uses
  System.SysUtils,Math;

   const n = 4;
   const m = 15;
   Type Tmas = array [1..n] of integer;
   Type Tmasresult = array [0..m] of integer;

  var A,B:TMAS;
      Aresult,Bresult:Tmasresult;
      ResultIndex,Acurrent,Bcurrent,ResultCount,i,j,IncreaseSize:integer;


begin
 A[1]:=1; A[2]:=2;  A[3]:=3;  A[4]:=5;
 B[1]:=1; B[2]:=3;  B[3]:=3;  B[4]:=5;

 Resultindex:=1;
 ResultCount:=1;
 Aresult[0]:=0;
 Bresult[0]:=0;
 i:=1;

     while i<n do

    begin
     Aresult[ResultIndex]:=A[i];
     Bresult[ResultIndex]:=B[i];
     ResultIndex:=ResultIndex+1;
     IncreaseSize:=0;
     j:=0;
      while j<ResultCount do
        begin
        Acurrent:=A[i]+Aresult[j];
        Bcurrent:=B[i]+Bresult[j];

        Aresult[ResultIndex]:=Acurrent;
        Bresult[ResultIndex]:=Bcurrent;

        ResultIndex:=ResultIndex+1;
        IncreaseSize:=IncreaseSize+1;
        j:=j+1;
        end;
       ResultCount:=ResultCount+IncreaseSize+1;


      i:=i+1;



    end;


     for i := 1 to m do
       Write(Aresult[i], ' ' );
     writeln;
     for i := 1 to m do
       Write(Bresult[i], ' ' );
     readln;

end.
