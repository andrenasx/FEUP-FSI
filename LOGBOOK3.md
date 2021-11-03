# Trabalho realizado na Semana #3

## Identificação

- CVE-2014-4114 (aka "Sandworm"). Permite que attackers executem código arbitrário no contexto do utilizador atual. Se o usuário atual estiver conectado com direitos de *admin*, um invasor poderá instalar programas; visualizar, alterar ou excluir dados; ou criar novas contas com direitos totais.
- O ataque é feito por meio de um objeto OLE criado em um documento do Office. Um objeto OLE (Object Linking and Embedding) é um componente da Microsoft que permite ligar dinamicamente arquivos e aplicativos.
- O sistema operativo afetado foi a Microsoft, entre as seguintes versões: Microsoft Windows Vista SP2, Windows Server 2008 SP2 e R2 SP1, Windows 7 SP1, Windows 8, Windows 8.1, Windows Server 2012 Gold e R2, e Windows RT Gold e 8.1.
- O CVE presente é do tipo de CWE-20: Improper Input Validation, isto é, um componente não valida ou valida incorretamente inputs, que pode afetar o fluxo de um programa.

## Catalogação

- Reportado a 12 de Junho de 2014.
- Não foi identificado quem descobriu a vulnerabilidade, nem se foi num programa de bug-bounty.
- CVSS score: 9.3 (máximo 10).

## Exploit

- Nome: Microsoft Windows - OLE Package Manager Code Execution
- Existe automatação feita com Metasploit, usando python2 e um script em python 2.7 que injeta código num objeto OLE num ficheiro ppsx (PowerPoint).
- Funciona em Windows: versões Vista SP2 até 8. Em versões de Office 2013 e 2010 SP2.
- Como funciona: É criado um ficheiro OLE binário, que fica imbutido num ficheiro ppsx, que é enviado à vítima.

## Ataques

- *Sandworm attack,* uma *zero-day vulnerability,* explorado desde Junho até Outubro de 2014
- Acredita-se que foi usado em *cyber attacks*, por um grupo Russo de espionagem cibernética, contra a NATO, União Europeia, Telecomunicações e Setores de Energia.

# Sources:

[https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2014-4114](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2014-4114)

[https://www.cvedetails.com/cve-details.php?t=1&cve_id=CVE-2014-4114](https://www.cvedetails.com/cve-details.php?t=1&cve_id=CVE-2014-4114)

## Identificação

[https://docs.microsoft.com/en-us/security-updates/securitybulletins/2014/ms14-060](https://docs.microsoft.com/en-us/security-updates/securitybulletins/2014/ms14-060)

[https://www.cvedetails.com/cwe-details/20/cwe.html](https://www.cvedetails.com/cwe-details/20/cwe.html)

[https://en.wikipedia.org/wiki/Object_Linking_and_Embedding](https://en.wikipedia.org/wiki/Object_Linking_and_Embedding)

## Exploit:

[https://www.exploit-db.com/exploits/35235](https://www.exploit-db.com/exploits/35235)

[https://www.exploit-db.com/exploits/35216](https://www.exploit-db.com/exploits/35216)

[https://docs.microsoft.com/en-us/security-updates/securitybulletins/2014/ms14-060#vulnerability-in-windows-ole-could-allow-remote-code-execution-3000869](https://docs.microsoft.com/en-us/security-updates/securitybulletins/2014/ms14-060#vulnerability-in-windows-ole-could-allow-remote-code-execution-3000869)

## Ataques

[https://www.trendmicro.com/en_us/research/14/j/an-analysis-of-windows-zero-day-vulnerability-cve-2014-4114-aka-sandworm.html](https://www.trendmicro.com/en_us/research/14/j/an-analysis-of-windows-zero-day-vulnerability-cve-2014-4114-aka-sandworm.html)

[https://www.mcafee.com/blogs/other-blogs/mcafee-labs/bypassing-microsofts-patch-sandworm-zero-day-root-cause/](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/bypassing-microsofts-patch-sandworm-zero-day-root-cause/)

[https://www.proficio.com/sandworm-microsoft-windows-zero-day-vulnerability/](https://www.proficio.com/sandworm-microsoft-windows-zero-day-vulnerability/)
