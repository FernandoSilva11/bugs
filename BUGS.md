# Bug 001 – Inscrição – Cursos de Pós-graduação sendo exibidos juntos com de Graduação.
## Descrição
Na tela de seleção de cursos, os cursos de Pós-graduação estão sendo exibidos juntos com o de Graduação.
1.	Ambiente
https://developer.grupoa.education/subscription/

2.	Passos para reprodução
   
      2.1	– Acessar o ambiente informado no item 1.
      
      2.2	– Selecionar Nível de ensino - Exemplo 'Graduação'
      
      ![image](https://github.com/user-attachments/assets/a0dd0602-34b6-440c-94fa-08ab60f9ede3)
      
      2.3	Clicar na caixa de seleção ‘Selecione um curso’.
      
      ![image](https://github.com/user-attachments/assets/ba582430-272b-47d2-9666-50d6f065d788)
      
      3.	Resultado esperado:
      	Sistema deveria trazer uma lista de cursos de Graduação 
          * Administração, 
          * Análise e Desenvolvimento de Sistemas, 
          * Ciência da Computação, Ciência de Dados, 
          * Direito, Engenharia Civil, 
          * Engenharia de Produção, Engenharia Elétrica, 
          * Engenharia Mecânica, Engenharia Química, 
          * Engenharia de Software, 
          * Gestão de Tecnologia da Informação, 
          * Nutrição, Psicologia, 
          * Redes de Computadores, 
          * Segurança da Informação, 
          * Sistemas de Informação, Tecnologia da Informação
      
          
      4.	Resultado obtido:
      	Além dos cursos de graduação, sistema retornou também cursos de Pós-Graduação 
          * Mestrado em Ciência da Computação, 
          * Mestrado em Engenharia de Software, 
          * Mestrado em Inteligência Artificial, 
          * Doutorado em Ciência da Computação, 
          * Doutorado em Engenharia de Software, 
          * Doutorado em Inteligência Artificial, 
          * Especialização em Segurança da Informação, 
          * Especialização em Ciência de Dados, 
          * Especialização em Blockchain, 
          * Especialização em Computação em Nuvem
      
      ![image](https://github.com/user-attachments/assets/165c6c67-63c9-402f-90d5-e62850187212)
      
Observação:
Ao analisar o html do sistema com dev tools foi possível identificar onde está o erro.
O arquivo index-C5vgy-VG.js que é carregado quando fazemos acesso na página ‘https://developer.grupoa.education/subscription/’ apresenta valores que deveriam estar apenas em Pós-graduação, mas estão sendo exibidos ao selecionar graduação. 
![image](https://github.com/user-attachments/assets/295a61d2-8e06-42c9-a020-831a5afce23e)

Evidencia undergraduate = graduação e gratuate = Pós-graduação.
![image](https://github.com/user-attachments/assets/38de9fee-231f-486a-8ce5-5fc354d04ad5)

 
Solução = remover os valores abaixo do ‘UndergradCombo’:
* Mestrado em Ciência da Computação
* Mestrado em Engenharia de Software
* Mestrado em Inteligência Artificial
* Doutorado em Ciência da Computação
* Doutorado em Engenharia de Software
* Doutorado em Inteligência Artificial
* Especialização em Segurança da Informação
* Especialização em Ciência de Dados
* Especialização em Blockchain
* Especialização em Computação em Nuvem


# Bug 002 - Dados Cadastrais - Campos númericos permitem letras e caractres especiais.

## Descrição
Na tela de inserção de dados pessoais, os campos 'Celular', 'Telefone' e 'CEP' permitem que sejam inseridas letras, porem esses campos deveriam receber apenas números.

1.	Ambiente
https://developer.grupoa.education/subscription/

2.	Passos para reprodução
         
      2.1	– Acessar o ambiente informado no item 1.
      
      2.2	– Selecionar Nível de ensino - Exemplo 'Graduação'
      
      ![image](https://github.com/user-attachments/assets/5772c011-cf02-4458-b907-5b49dcb64811)
      
      2.2 Selecionar  Curso - Exemplo 'Psicologia' e clicar em 'Avançar'
      
      ![image](https://github.com/user-attachments/assets/12b167e6-a43a-4e20-a406-575d8ce68591)
      
      ![image](https://github.com/user-attachments/assets/f7dd78e8-1480-4ab6-8604-2cada0690d84)
      
      2.3 Preencher campo Celular com letras - Exemplo 'teste1234@'
      
      ![image](https://github.com/user-attachments/assets/22b1fe56-5714-48a3-8cb2-18589be5da7b)

  	  2.4 Prencher campo Telefone com letras - Exemplo 'teste5678!'
  	
      ![image](https://github.com/user-attachments/assets/395370a3-5c7d-497b-8d7a-c1271133b714)

      2.5 Prencher campo CEP com letras - Exemplo '1234567$'
      
      ![image](https://github.com/user-attachments/assets/26624b61-7cf6-4fa1-9422-06b56ee501a2)
      
      Resultado esperado
  	
       Sistema deviria impedir que fossem inseridas letras nesses campos.
  	
      Resultado obtido
  	
       Sistema não identifica inconsistência e até permite o cadastro com este dados incorretos.
      
      
      
