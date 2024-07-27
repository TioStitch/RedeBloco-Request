🕹 **REDE BLOCO - REQUEST**
> Os arquivos estão em testes e não há uma previsão de quanto em quanto tempo há de serem atualizados para versões recentes.
> O estado atual dos arquivos permanece como o mais recente atualmente.

🔩 **Por que decidimos criar isto**
- Sabendo que há desenvolvedores que gostam de cooperar com o progresso e eficácia da jogabilidade de jogadores ou de si mesmos, decidimos criar esta válvula de escape para obter-se informações estáticas do Sky Block.


🧪 **Direto ao código**
- Abaixo há alguns exemplos de como deve-se utilizar estas informações.

**Informações disponíveis**
> (Coleções, Encantamentos e Entidades)

🐍 **PYTHON**

  REQUISITOS:
  - lib requests (https://pypi.org/project/requests/)

```python
import requests;

data = requests.get("https://tiostitch.github.io/RedeBloco-Request/collections.json").json();

quartz_map = data["collections"]["QUARTZ"]

quartz = quartz_map["name"]
quartz_max_level = quartz_map["maxLevel"]

print(
"Informações da Coleção:\n"
"\nColeção:", quartz,
"\nNível Máximo:", quartz_max_level
)
```

☕ **JAVA**

  REQUISITOS:
  - lib para conexão HTTP

```java
    private static final String CONNECT_LINK = "https://tiostitch.github.io/RedeBloco-Request/collections.json";

    public static void main(String[] args) throws IOException {

        final URL url = new URL(CONNECT_LINK);
        final HttpURLConnection connection = (HttpURLConnection) url.openConnection();
        connection.setRequestMethod("GET");

        System.out.println(getContent(url));
    }

    private static String getContent(URL preparedUrl) {
        try {
            final InputStream inputStream = preparedUrl.openStream();
            final BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(inputStream, StandardCharsets.UTF_8));
            return readContent(bufferedReader);
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
    }

    private static String readContent(BufferedReader reader) {
        try {
            final StringBuilder content_builder = new StringBuilder();
            String inputLine;

            while ((inputLine = reader.readLine()) != null) {
                content_builder.append(inputLine);
                break;
            }

            return content_builder.toString();
        } catch (IOException ignored) {
            return "";
        }
    }
```
