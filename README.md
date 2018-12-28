#Corrigindo erros nodejs

npm cache clean, npm install jquery (to my app folder)

npm install --save jquery

npm install jquery -g

npm rebuild

sudo npm install jquery -g

sudo npm install jquery

export NODE_PATH=/usr/local/lib/node_modules

# consulta_cep_bolado

https://bognarjunior.wordpress.com/2016/01/12/rotas-com-nodejs/



/*
Prineiro forma de requisicao
var http = require('http');
http.createServer(function(req,res) {
  res.writeHead(200, { 'Content-Type': 'text/plain; charset=utf-8' }); 
  res.write('Olá mundo!');
  res.edn();
}).listen(3000);
console.log('Servidor iniciado!');
*/

'use strict';

var nodeStatic = require('node-static');
var http = require('http');

//var socketIO = require('socket.io');


var fileServer = new(nodeStatic.Server)();


var app = http.createServer(function(req, res) {
    fileServer.serve(req, res);

res.writeHead(200, {"Content-Type":"text/html; charset=utf-8"});
//res.writeHead(200, { 'Content-Type: text/html; charset=utf-8' }); 
  
if (req.url == "/") {
        //response.write("<h1>Hello World!</h1>");
    console.log("/");
    }else if(req.url=="/index"){
    	console.log("/index")
    } else if (req.url == "/next") {
    console.log("next");
  
        //response.write("<h1>Página 2</h1>");
    } else {
        //response.write("<h1>Url não encontrada</h1>");
    
//res.redirect('http://www.google.com');

   // res.writeHead(302, {
  	//	'Location': 'http://www.google.com'

  	//	});
    console.log("URL Erro");
    }


    //Rota da pagina que esta sendo requisitada
    //TODO: Armazenar rota em uma lista mantendo o log de tudo que foi acessado durante a requisicao
    //TODO: ARMAZENAR UMA LISTA FAZER UM LOG CONTROLANDO OS DISPAROS QUE FORAM FEITOS
    //TODO; USAR ISSO PRA PEGAR AS REQUISICOES -
    console.log(' + Requisicao em: http://localhost:8080' + req.url);


       // res.redirect('/view/video.html');
//TODO:VALIDAR A ROTA
//    if(req.url == "/"  && req.url == "/public/main.css" && req.url=="/public/main.css" && req.url == "/public/images/video.png" && "public/images/close.png" && req.url == "/js/main.js"){

        console.log(' + Requisicao em: http://localhost:8080' + req.url);
        console.log('STATUS_CODE:'+ res.statusCode);



  //  }
    /*else{

        res.write("<h1>!Erro 4000</h1>");
    }*/



    }).listen(8080);






Consulta CEP_bolado foi criado pra demonstrar como se consome webservice de forma simples validando cep 
Neste momento vou usar apenas o ws dos correios. 
Pretendo consumir ws do IBGE

/*
  .--.,                                                              
,--.'  \                                 ,---,               __  ,-. 
|  | /\/                 ,----._,.   ,-+-. /  |            ,' ,'/ /| 
:  : :      ,--.--.     /   /  ' /  ,--.'|'   |    ,---.   '  | |' | 
:  | |-,   /       \   |   :     | |   |  ,"' |   /     \  |  |   ,' 
|  : :/|  .--.  .-. |  |   | .\  . |   | /  | |  /    /  | '  :  /   
|  |  .'   \__\/: . .  .   ; ';  | |   | |  | | .    ' / | |  | '    
'  : '     ," .--.; |  '   .   . | |   | |  |/  '   ;   /| ;  : |    
|  | |    /  /  ,.  |   `---`-'| | |   | |--'   '   |  / | |  , ;    
|  : \   ;  :   .'   \  .'__/\_: | |   |/       |   :    |  ---'     
|  |,'   |  ,     .-./  |   :    : '---'         \   \  /            
`--'      `--`---'       \   \  /                 `----'             
                          `--`-'                                 

*/

Crie o banco de dados no Mysql
user:root
senha:123456
CREATE DATABASE `bancodedados`;

CREATE TABLE  `bancodedados`.`contatos` (
  `id` int(10) unsigned NOT NULL auto_increment,
  `nome` varchar(200) NOT NULL default '',
  `email` varchar(200) NOT NULL default '',
  `telefone` varchar(45) NOT NULL default '',
  PRIMARY KEY  (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

select * from  contatos;




jquery
https://pt.stackoverflow.com/questions/28713/insert-mysql-usando-ajax

 var url = 'http://www.petfy.com.br/android/addUsuario.php';
            $.ajax({                                      
                url: url,
                type: "POST", 
                data:{
                    nome: nome, email: email, senha: senha, telefone: telefone, endereco: endereco, estado: estado, cidade: cidade
                },
                success: function(rows){
                    rows = $.parseJSON(rows);
                    for (var i in rows){    
                        var row = rows[i],          
                            id = row[0], 
                            nome = row[1]; 
                            alert(nome);
                    }       
                },
                error: function(rows){
                    alert('erro');
                }
            });
        });
