🕹 **REDE BLOCO - REQUEST**
> Os arquivos estão em testes e não há uma previsão de quanto em quanto tempo há de serem atualizados para versões recentes.
> O estado atual dos arquivos permanece como o mais recente atualmente.

🔩 **Por que decidimos criar isto**
- Sabendo que há desenvolvedores que gostam de cooperar com o progresso e eficácia da jogabilidade de jogadores ou de si mesmos, decidimos criar esta válvula de escape para obter-se informações estáticas do Sky Block,


🧪 **Direto ao código**
- Abaixo há alguns exemplos de como deve-se utilizar estas informações.

**Informações disponíveis**
> (Coleções, Encantamentos e Entidades)

🐍 **PYTHON**

  REQUISITOS:
  - lib requests

```python
import requests;

data = requests.get("https://tiostitch.github.io/RedeBloco-Request/collections.json").json();

quartz_map = data["collections"]["QUARTZ"]

quartz = quartz_map["name"]
quartz_max_level = quartz_map["maxLevel"]
quartz_rewards = quartz_map["rewards"]

print(
"Informações da Coleção:\n"
"\nColeção:", quartz,
"\nNível Máximo:", quartz_max_level
)
```
