## Reposit�rio Oficial do Projeto MedicalManagement-Sys

### Este projeto � o Caso de Uso do nosso Curso de Asp.NetCore MVC - Do Zero ao Ninja

> *__Tela Inicial criada em 02-01-2020. Est� no Release 0.10.1. Confira l�:__*

![Tela Inicial do Projeto MedicalManagenet-Sys](https://user-images.githubusercontent.com/1213751/71663844-87052780-2d35-11ea-95c0-623a74885ebc.png "Antes do Dashboard")


### DataCadastro:

> Todo: O campo DataCadastro deve ser inclu�do automaticamente, mas n�o deve ser alterado. Este processo ser� implementado no contexto da aplica��o.

---

### Controle de Vers�o:

> __Fim do M�dulo B�sico e Intermedi�rio__:  *Preimeiro pr�-release com todo o M�dulo B�sico e Parte do Intermedi�rio, at� a Migra��o do Asp.Net Core 2.2 para as vers�es 3.0.0 e 3.1.0*

- Pr�-Release v.0.9.0: **[Acesse Aqui](https://github.com/carlosItDevelop/CursoAspNetCoreUdemy/releases/tag/CursoAspNetCoreUdemy)**.

> __Tela Inicial e Corre��o de Bug__:  *Pr�-Release com a Cria��o da Tela Inicial do Projeto e Corre��o de Bug (Atualiza��o de .CSHTML em Runtime).*

- Pr�-Release v.0.10.1: **[Acesse Aqui](https://github.com/carlosItDevelop/CursoAspNetCoreUdemy/releases/tag/Atualizacao_TelaInicial)**.

> __In�cio da �ltima se��o antes do M�dulo B�nus (Arquitetura de Software), Polular Tabelas Iniciais, Importa��o de .CSV e Corre��o de Bugs__:

- Pr�-Release v.0.11.0: **[Acesse Aqui](https://github.com/carlosItDevelop/CursoAspNetCoreUdemy/releases/tag/ImportCSV)**

---

> ### TaskList - Tag Helpers

 Feature														| Complexidade	| Status	
---------------------------------------------------------------	| -------------	| --------	
 Criar uma Tag Helper para exibir um e-mail no Rodap�			| Alta			| Ok		
 Podemos usar um dom�nio padr�o ou um parametrizado				| Alta			| Ok		
 Vamos customizar a Tag Html "a", usando, inclusive, o mailTo	| Normal		| Ok		
 Preciso de uma classe com o sufixo Tagelper					| Baixa			| Ok
 Preciso que a classe acima Herde de TagHelper					| Alta			| Ok
 Package: using Microsoft.Asp.NetCore.Razor.TagHelpers			| Baixa			| Ok
 Essa class precisa sobrescrever a Task ProcessAsync			| M�dia			| Ok
 Par�metros: (TagHelperContext context, TagHelperOutput output)	| M�dia			| Ok
 Neste exemplo vamos deixar o context de lado					| Baixa			| Ok
 Usaremos um dom�nio default ou receberemos no par�metro		| Normal		| OK
 Usaremos a nota��o Kebab Case: MeuEmail  => meu-email			| Baixa			| Ok

---

### C�digo pronto do nosso EmailTagHelper

```CSharp
using System.Threading.Tasks;
using Microsoft.AspNetCore.Razor.TagHelpers;

namespace Cooperchip.ITDeveloper.Mvc.Extentions.TagHelpers
{
    public class EmailTagHelper : TagHelper
    {
        public string Domain { get; set; } = "eaditdeveloper.com.br";
        public override async Task ProcessAsync(TagHelperContext context, TagHelperOutput output)
        {
            output.TagName = "a";
            var content = await output.GetChildContentAsync();
            var target = content.GetContent() + "@" + Domain;
            output.Attributes.SetAttribute("href", "mailto:" + target);
            output.Content.SetContent(target);
        }
    }
}
```

### Migrando nossa aplica��o do Asp.Net Core 2.2 para 3.0 / 3.1.


>> Se voc� for um iniciante em Asp.Net Core talvez nunca tenha ouvido falar de AddMvcCore().


Consultar a documenta��o para TagHelpers e ViewComponents, **[Leia aqui](https://docs.microsoft.com/pt-br/)**.
Consultar a documenta��o para MarkDown, **[Leia aqui](http://daringfireball.net/projects/markdown/basics)**.

---

> Quer conhecer nosso projeto? Acesse o curso na Udemy:  **[Acesse aqui](https://www.udemy.com/course/curso-de-aspnet-core-mvc-2-2-do-zero-ao-ninja/?referralCode=41B345D11D74CEDD7E57)**.

