<h1>
    <a href="https://www.dio.me/">
     <img align="center" width="40px" src="https://hermes.digitalinnovation.one/assets/diome/logo-minimized.png"></a>
    <span> Trabalhando com Análise de Sentimentos com Language Studio no Azure AI </span>
</h1>

Repositório desenvolvido para fins didáticos. 

Parte de um conjunto de labs do Bootcamp Microsoft Azure AI Fundamentals da [Digital Innovation One](https://www.dio.me/).

Este repositório responde ao desafio no lab  **Análise de Sentimentos com Language Studio no Azure AI** 

[![Link do Lab](https://img.shields.io/badge/▶-000?style=for-the-badge&logo=movie&logoColor=E94D5F)](https://web.dio.me/lab/analise-de-sentimentos-com-language-studio-no-azure-ai/learning/f6884c74-e7aa-4700-a84b-a3446e0b6d8d) 
[![Link do Lab](https://img.shields.io/badge/Acesse%20o%20Lab%20na%20Plataforma-E94D5F?style=for-the-badge)](https://web.dio.me/lab/analise-de-sentimentos-com-language-studio-no-azure-ai/learning/f6884c74-e7aa-4700-a84b-a3446e0b6d8d)

## Objetivo 🎯
Neste LAB, exploraremos o uso do Azure Speech Studio e a análise linguística proporcionada pelo Language Studio. Durante a prática, teremos a oportunidade de aprofundar nosso entendimento sobre como aproveitar essas ferramentas avançadas da Microsoft Azure. 
Estaremos focados em aprimorar nossas habilidades na implementação de soluções de análise de fala e linguagem, abrindo portas para uma compreensão mais ampla e prática das capacidades oferecidas por essas tecnologias inovadoras.

  -- Autora do lab na DIO: Valéria Baptista   /  Head of Cloud and Cybersecurity, CloudData Tech & DevOps

### Azure

Os elementos testados fazem parte da suite de inteligência artificial do Azure AI services. 
Então uma sequencia de passos é necessária:

-- Ter uma conta na Azure. Acesso o  Azure portal no link https://portal.azure.com

-- Ter uma assinatura válida (signature). É possível testar por 1 mês com 200 dólares de crédito.


### IA do Azure Speech Studio

Na primeira parte do lab usaremos o Estúdio de Fala

-- acessar o link : https://speech.microsoft.com/portal

No canto superior direito clicar na engrenagem para acessar as "Configurações"

Caso não tenha nenhum recurso disponível, clicar em novo recurso:

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/18f85582-e59a-42d3-a83b-4dc78e3c52eb)

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/1a339e14-756f-4af3-8bf6-8bb9d7af6abf)

Clicar para selecionar o recurso criado.


### Vamos experimentar a opção Conversão de fala em texto em tempo real:

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/f8cdf94c-a3e9-4457-84aa-5a88db9d5185)


Lembrar de marcar que você reconhece que esta ferramenta usará um recurso (opção que confirma que você reconhece que poderão incorrer custos na sua conta).

Selecionar o idioma do audio a ser testado. Como foi utilizado o audio da documentação o idioma permaneceu o inglês.

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/9a57c88b-3941-4f0f-872f-a58646ca417a)

No Studio de Fala temos vários exemplos de como aplicar a tecnologia para nosso dia a dia:

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/e991210e-06b9-40a3-b96a-3e022ee37708)

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/1bc1b7da-1549-42da-b713-683e937bb54a)

Bem como instruções de precificação e instruções de uso responsável da IA.

A Microsoft disponibiliza um bom conteúdo de exemplos no GitHub de como utilizar o Estudio de Fala neste link: 

https://github.com/Azure-Samples/cognitive-services-speech-sdk


### IA do Azure Language Studio

#### É preciso criar um recurso do Language Service

1o. Acessar o Portal do Azure e criar um recurso do tipo Language Service

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/3484727d-e1a9-4ff2-93e0-f237f42185e4)

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/6b9a3124-b92c-46fa-9fb8-ef45b087daf2)

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/de113417-6bf5-4d4b-8bb9-7b3648dd1448)

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/e4ea648a-403b-4999-9612-1b0c83521803)

Depois do deploy complete acessar direto a página:

https://language.cognitive.azure.com/

E selecionar o recurso recem criado dentro do Portal do Azure:

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/b61ba5aa-e2df-4662-add5-05b5f408883f)


### Vamos criar um projeto para Classificar texto e opiniões / sentimento:

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/9ad44c66-e1cb-4d3d-862a-dfbc758ae361)


O texto usado para o exemplo foi retirado da documentação oficial de apoio deste lab : 

https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/06-text-analysis.html

"
 Tired hotel with poor service
 
 The Royal Hotel, London, United Kingdom
 
 5/6/2018
 
 This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
"


![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/55a296e8-1079-49ec-9602-848e82603bb5)


##### Análise dos resultados:
Interessante observar como a ferramenta foi capaz de perceber o tom de desagrado do comentário do texto:

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/d8072596-ac26-4092-ab86-4c5269bd1602)

E na explicação realça como chegou nas conclusões de sentimento:

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/0d7a3356-92b7-426a-a6f5-a7280daabb4d)

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/3078888b-e334-4160-ade1-886f511aa4f4)

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/641bb683-b522-4d83-b597-5700f535e499)

![image](https://github.com/toniacprado/DIO-Analise-de-Sentimentos-com-Language-Studio-no-Azure-AI/assets/105946569/9908b9a2-34b7-415f-a8de-3337f6043bc0)


O portal já tras exemplos de como utilizar em aplicação com a documentação no gihub:  

https://github.com/Azure/azure-sdk-for-python/tree/main/sdk/textanalytics/azure-ai-textanalytics/samples

E também explica os preços e as boas práticas de IA responsável.

### Considerações Finais
O laboratório foi muito instrutivo para apresentar as funcionalidade de fala e análise de texto, apesar de serem recursos visivelmente avançados o uso da ferramenta foi amigável e com ampla documentação de apoio para aplicar em projetos práticos!

Toni A C Prado


----
Foi usado como base as aulas do Bootcamp e as instruções dos links:

https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/09-speech.html

https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/06-text-analysis.html

O audio usado foi o fornecido no link:  https://aka.ms/mslearn-speech-files to download speech.zip



