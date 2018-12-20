# consulta_cep_bolado

Consulta CEP_bolado foi criado pra demonstrar como se consome webservice de forma simples validando cep 
Neste momento vou usar apenas o ws dos correios. 
Pretendo consumir ws do IBGE

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
