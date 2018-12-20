# consulta_cep_bolado

Consulta CEP_bolado foi criado pra demonstrar como se consome webservice de forma simples validando cep 
Neste momento vou usar apenas o ws dos correios. 
Pretendo consumir ws do IBGE

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
