# transfer_learning_dio
# Instalação

- Python 3.12.11
- Suba a pasta requirements para o diretório:
-"/content/sample_data" dentro do colab
- Instalar dependências:
- !pip install -r requirements.txt
 
- Baixe o dataset no seguinte endereço:
-"https://www.microsoft.com/en-us/download/details.aspx?id=54765"
- Suba o arquivo "kagglecatsanddogs_5340.zip" para o seguinte caminho:
- "/content/sample_data/kagglecatsanddogs_5340.zip"

- Execute célula por célula


- Na útima célula:
 # Caminho da imagem que você quer testar
img_path = "Caminho_da_sua_imagem" localize essa variável no código e escolha o caminho da sua imagem para poder testar o modelo treinado

## Ajustes feitos no projeto

- Dataset adicionado manualmente no Colab (link original estava quebrado).
- Redução do tamanho das imagens para **96x96** para diminuir o consumo de memória.
- Uso de `EarlyStopping` para evitar OOM durante o treinamento.
- Ajuste do `batch_size` para **16** e `epochs` para **50**, garantindo maior estabilidade.
- Configurações adicionais foram testadas, mas resultaram em OOM.


