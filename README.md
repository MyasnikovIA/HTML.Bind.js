# HTML.Bind.js
Библиотека для замены встроенных механизмов обмена данными между клиентом и сервером

Имортировать класс HTML.Bind.js.xml

Подключение В CSP:
<pre>
  <head>
    <script language="JavaScript" type="text/javascript" src="/csp/broker/cspxmlhttp.js"></script>
    <script language="JavaScript" type="text/javascript" src="/csp/broker/cspbroker.js"></script>
  </head>
    <script type="text/javascript" src="#($SYSTEM.CSP.GetDefaultApp($ZU(5)))#/#($zcvt("HTML.Bind.js","O","URL"))#.cls"></script>  
    ****
</pre>

Подключение В Классах:
<pre>
Class User.del333 Extends %CSP.Page
{
   ClassMethod OnPage() As %Status
   {
      &html&lt;
           &lt;script language='JavaScript' type='text/javascript' src='#($SYSTEM.CSP.GetDefaultApp($ZU(5)))#/#($zcvt("HTML.Bind.js","O","URL"))#.cls' &gt; &lt;/script&gt;   
           <script language='javascript'> 
              GerReportFile=function(){ 
                var texts=['param1','param2','param3']; 
                try { 
                    var res=#server(Dogovor.Bill.ProntPdf.SchetOne.ShowReportWeb('pdf',JSON.stringify(texts)))#;
                    eval(res);
                }catch (e) {
                    console.log(res);
                }   ; 
              }   
            </script> 
            &lt;button  onclick='GerReportFile()' &gt; GerReportFile &lt;/button&gt; 
     &gt; 
  Quit $$$OK
}

}


</pre>





