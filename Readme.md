![Static Badge](https://img.shields.io/badge/Inteligência_Artificial_(IA)-blue)
![Static Badge](https://img.shields.io/badge/Documment_Intelligence-blue)
![Static Badge](https://img.shields.io/badge/Indexing-blue)
![Static Badge](https://img.shields.io/badge/Microsoft_Azure-blue)
![Static Badge](https://img.shields.io/badge/Azure_Cognitive_Search-blue)
![Static Badge](https://img.shields.io/badge/Azure_AI_Search_Index-blue)

## Introdução


O objetivo desse laboratório é testar algumas ferramentas de indexação, pesquisa e *document intelligence* com o recurso Azure AI Search. Esses procedimentos foram realizados como parte do **Bootcamp Microsoft Azure AI Fundamentals, da DIO**.


**Document Intelligence** é uma das áreas em que a aplicação de **inteligência artificial** se mostra muito útil e eficaz. É um conceito que envolve a aplicação de diversas ferramentas de **processamento de documentos**, tornando possível **extrair suas informações** de forma muito mais eficiente ao permitir o **entendimento do que elas representam**. Dentre essas ferramentas, pode-se citar o uso de OCR (Optical Character Recognition), a fim de identificar texto em imagens de recibos ou outros documentos digitalizados; indexação de conteúdos, o que os torna pesquisáveis dentro de uma base de dados; extração de frases-chave e dados de forma automática e até mesmo análise de sentimentos, como em casos de comentários e avaliações.


Nesse laboratório, utilizo algumas técnicas de Document Intelligence para desenvolver uma solução de ***mining knowledge***, a fim de obter *insights* de avaliações de consumidores de uma loja de café fictícia. Isso foi feito construindo um **Azure AI Search index** através dessas avaliações.


Esses experimentos foram baseados nos guias da Microsoft Learn. Para informações mais detalhadas, consulte a página [Explore an Azure AI Search index (UI)](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html).


## Procedimento
Para realizar o procedimento de Document Intelligence desse exercício são necessários três recursos Azure: **Azure AI Search**, **Azure AI Services** e **Storage account**.


![image](https://github.com/user-attachments/assets/51b98b36-4c90-4b13-b230-297284f19943)


- Azure AI Search: esse recurso gerencia a indexação e pesquisa dos documentos.
- Azure AI Services: esse recurso contém as funcionalidades de IA necessárias para enriquecer os dados dos documentos com insights.
- Storage account: É o recurso no qual os documentos estão armazenados (em *blob containers*).


### Upload dos dados e criação do Index


As *reviews*, ou avaliações, utilizadas nesse experimento estão disponíveis [nesse link](https://aka.ms/mslearn-coffee-reviews). Uma vez criado o container de armazenamento, foi feito o upload das avaliações para o mesmo.

![image](https://github.com/user-attachments/assets/4a7965d2-f573-48c5-842d-cb3296998cd0)

Com os documentos no armazenamento, temos tudo pronto para utilizar o Azure AI Search para criar um *index* e começar a extrair *insights* dos documentos. Isso pode ser feito através de um assistente presente no portal Azure, na visão geral do recurso.


![image](https://github.com/user-attachments/assets/de6be33a-fd52-4fb3-b7b1-0ea85a87b876)


Nessa etapa, é importante selecionar o *storage* em que os documentos estão armazenados, bem como as *skills* que serão usadas para enriquecer a extração de conhecimento dos documentos. Existem diversas *skills* disponíveis, é preciso selecionar aquelas que se adequam melhor ao contexto dos documentos analisados.


### Pesquisas (queries) no Index
O recurso Azure AI Search também fornece um assistente para realizar pesquisas no Index recém criado. Os resultados são retornados em JSON.

![image](https://github.com/user-attachments/assets/d806f4ff-2328-4fef-8276-a16648dbb92d)

Na imagem abaixo, podemos ver uma pesquisa simples, filtrando os resultados que estão localizados na cidade de Chicago.

![image](https://github.com/user-attachments/assets/90b30fd2-329b-49c0-8b54-34b73029689d)

Podemos ir além e pesquisar pelas avaliações que possuem um tom negativo de acordo com a análise de sentimentos extraída dos documentos.

![image](https://github.com/user-attachments/assets/3f565bf2-7ba7-4bae-8076-0207af44cccf)


É interessante notar ainda as frases-chave (*keyphrases*) extraídas das avaliações. São sentenças, ou palavras chave, também obtido no processo de enriquecimento, que tentam extrair o máximo de significado do texto analisado. Apenas por meio delas é possível ter uma boa compreensão sobre o sentido geral da avaliação.


## Conclusão e Insights
Na era da informação, não basta apenas ter terabytes de dados sem ser capaz de analisá-los e extrair algo disso. É nesse contexto que as técnicas de Document Intelligence se destacam. Através dessas ferramentas é possível tornar úteis e valiosas as informações em massa que não poderiam ser analisadas individualmente por pessoas. A análise desses grandes conjuntos de dados podem revelar insights valiosos para empresas que os detém, o que faz dessa área muito proveitosa no presente contexto.
