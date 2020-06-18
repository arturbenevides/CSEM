Bem! Para você que busca trabalhar com dados de perfilagem de poços de petróleo e tem dúvidas da estrutura de dados armazenados, aqui pode ser um bom lugar para tirar algumas! 

## Perfis utilizados para estudos geofísicos
- Convencionais
GR (Gamma ray)
ILD (Deep Inductions Log)
DT (Wave slowness) 
SP (Spontaneous potential).
NPHI (Neutron porosity)
CAL (Caliper)
RHOD (Density)
BHT (Bottom-hole temperature)

Os dados são geralmente gravados em um formato conhecido como dLIS que é um arquivo de formatação binária ([excelente texto sobre esses tipos de dados e algumas formas de conversão](https://erlend-viggen.no/dlis-files/), sendo assim, podem ser lidos por meio de programas especificos ou convertidos para um arquivo de texto (.las).

A maioria dos softwares que importam dados .dlis não são gratuitos ([Log I/O](https://petroware.no/html/logio.html))ando são, não tem opção de exportar o dado em formato de leitura, como .las e ascii (por exemplo, [Well log viewer](http://www.starseis.com/index.php/lasviewer)).

Se você tem interesse em manipular as curvas dos perfis em seu estudo, temos algumas possibilidades:

No python você pode usar as bibliotecas dlisio e dlispy para leitura dos arquivos dlis e manuear diretamente sem a necessidade de um arquivo acessório .las (em outras palavras, você não precisa converter dlis para las e depois entrar no software).

Caso tenha interesse nos arquivos .las, alguns conversores podem ser utilizados:

**Conversores:**
Toolboxs Schlumberger

* Log Data Toolbox (DLIS to ASCII): Permite conversão facil dos arquivos com algumas opçoes de export interessante (uniformizar o depth step, visualizar rapidamente as profundidades mínimas e máximas de cada frame, e direção do indice de profundidade- aumentando ou diminuindo com as linhas).

<img src='https://github.com/arturbenevides/Well_log_analysis/blob/master/Toobox_log.png' width = 600>


* dLis browser (versão trial), não é posível uniformizar o depth step entre os perfis, eles serão separados em diferentes frames. Sem controle da direção do indice de profundidade e unidade de profundidade (feet or meters). O maior benefício desse software é a possibilidade de poder visualizar as curvas antes da conversão.


Após conversão dos dados, inúmeros programas facilitam o import e manuseio dos dados. Abaixo listo algumas bibliotecas que podem ser usadas no python.
- **Manusear aqrquivos .las**
* [**Lasio**](https://pypi.org/project/lasio/)
Excelente biblioteca com vários tutoriais

https://lasio.readthedocs.io/en/latest/

Log ASCII Standard (LAS) files in Python

* **Welly**
* **las2**
* [**Petropy**](https://pypi.org/project/petropy/)

- **Criar striplog dos perfis**

* [**Striplog**](https://pypi.org/project/striplog/0.7.1/)

**Outros dados**

Geralmente, os poços são acompanhados por:
Arquivo AGP: decrição litológica
Perfil composto: reune os principais perfis e a coluna estratigráfica em um pdf.
Dados direcionais
Checkshot
Sismica do poço
Relatório de teste de formação


## Problemas:
Nos arquivo dLIS, LAS ou até no perfil compostos, os nomes dos perfis não são os mesmos, tal qual nós estamos acostumados (GR, ILD etc.)

Neste site abaixo, você pode encontrar os nomes dos perfis a partir de seus mneumônicos:
http://fuzzylas.appspot.com/

Uma biblioteca em python pode ajuadar a localizar o seu perfil de interesse a partir dos seu dado:


