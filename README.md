# Fitopatologia e Visão Computacional: Detecção e Quantificação de Doenças

Este projeto entrega uma solução prática para avaliar a saúde foliar em culturas agrícolas, unindo a visão agronômica sobre o comportamento de doenças com inteligência artificial. O pipeline desenvolvido realiza duas tarefas centrais: quantifica a área lesionada da planta por meio de processamento de imagens e classifica o patógeno causador utilizando redes neurais convolucionais.

## Funcionalidades Implementadas

  * **Extração de Severidade (Visão Computacional Clássica):** Utiliza a biblioteca OpenCV para segmentar a folha no espaço de cores HSV. O algoritmo calibra a diferença visual entre o tecido verde saudável e as lesões biológicas, entregando a porcentagem exata de área foliar afetada.
  * **Classificação de Patógenos (Deep Learning):** Emprega a arquitetura MobileNetV2 por meio de Transfer Learning. O modelo identifica a doença específica e a cultura (como tomate, batata ou pimentão) com base nos padrões do dataset.
  * **Gestão de Persistência:** O script salva automaticamente os pesos do modelo após o treinamento inicial. Nas execuções seguintes, ele carrega o arquivo pronto, poupando capacidade computacional e tempo.
  * **Geração de Painel (Dashboard):** Processa lotes inteiros de imagens para simular um cenário de campo, plotando os resultados lado a lado e mostrando o diagnóstico, o nível de confiança preditiva e a máscara binária da lesão foliar.

## Estrutura do Repositório

O código foi desenhado em blocos lógicos numerados para facilitar a leitura técnica e a manutenção. A base de dados utilizada é gerenciada e baixada dinamicamente via `kagglehub` a partir da coleção `emmarex/plantdisease`, eliminando a necessidade de armazenar imagens pesadas no repositório.

## Como Instalar e Executar

1.  Faça o clone do repositório para o seu ambiente local:

    ```bash
    git clone https://github.com/rafaelnm90/visao_computacional.git
    cd desafio-visao-computacional
    ```

2.  Crie um arquivo com o nome `requirements.txt` na mesma pasta do projeto e adicione a seguinte lista de dependências:

    ```text
    tensorflow
    opencv-python
    numpy
    matplotlib
    kagglehub
    ```

3.  Instale as bibliotecas necessárias. Recomenda-se o uso de um ambiente virtual para manter as versões organizadas:

    ```bash
    pip install -r requirements.txt
    ```

4.  Execute o script principal:

    ```bash
    python main.py
    ```

## Controle de Treinamento e Logs

O pipeline possui variáveis de controle de fácil acesso localizadas no primeiro bloco do script, desenhadas para agilizar testes e demonstrações:

  * `EXIBIR_LOGS = True`: Mantém o console informando cada passo do processamento de forma limpa e profissional, sem poluição visual.
  * `FORCAR_RETREINAMENTO = False`: O comportamento padrão é utilizar o modelo já treinado e salvo localmente. Se houver a necessidade de treinar a rede do zero para avaliar a curva de aprendizado, basta alterar este valor para `True`.

## Apresentação Prática do Projeto
(https://colab.research.google.com/drive/1KvnH9AAkBo76m56HdPE2AFIMWslQUKx5?usp=sharing) | [Apresentação em Vídeo](https://www.youtube.com/watch?v=pIZvNwrLszA&t=1s)

## Autor

**Rafael Novais de Miranda**
[LinkedIn](https://www.google.com/search?q=https://www.linkedin.com/in/rafaelnovaism/) | [GitHub](https://www.google.com/search?q=https://github.com/rafaelnm90/) | [Currículo Lattes](https://www.google.com/search?q=http://lattes.cnpq.br/6450189926093594)
