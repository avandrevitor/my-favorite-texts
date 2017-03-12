[Melhores Práticas] Como passar configurações ao PHPUnit
========================================================

PHPUnit oferece muitas opções com vários parametros na linha de comando. No entanto, isto se torna chato e trabalhoso quando se digita mais de uma vez.

Por esta razão, você pode criar um [arquivo de configuração XML](http://www.phpunit.de/manual/current/en/appendixes.configuration.html) o [phpunit.xml](http://www.phpunit.de/manual/current/en/appendixes.configuration.html) que será automaticamente utilizada pelo binário phpunit.

Agora você deve querer incluir este arquivo de configuração em seus projetos com código fonte, para poder ser utilizado por todos os desenvolvedores participantes e também seu servidor de integração contínua. Mas como ?

## Bom, você poderia simplesmente commitar o arquivo phpunit.xml para seu repositório, certo ?

Sim, poderia. Mas, todos os desenvolvedores que quiserem trabalhar em seu projeto, devem fazer checkout é usar estas configurações ou passaram por problemas ao manter as alterações locais de configuração se não especificarem configurações diferentes por linha de comando.

## Não! Em vez disso, use phpunit.xml.dist.

[Sebastian me explicou isto](http://github.com/caefer/StreamHitching/commit/e1a6cef49ea6466403e3aea533728e04139e5d80) e ele está certo. Se você fornecer um phpunit.xm.dist(ribuição) ao invés disso, cada desenvolvedor pode escolher se quer utilizar a sua configuração ou a dela/dele.

Também é aconselhável ignorar o phpunit.xml em seu repositório usando `.gitignore` ou `svn:ignore` ou similar. Desta forma, todos podem usar as configurações ele/ela sem forçar os outros a utilizar também.

## Como meu servidor de integração contínua pode utilizar a configuração ?

Simples! O binário do phpunit tem inteligência suficiente para usar qualquer arquivo, ele usa phpunit.xml.dist se o arquivo phpunit.xml não estiver disponível.

link: [http://www.testically.org/2010/08/24/best-practice-how-to-ship-phpunit-configuration/](http://www.testically.org/2010/08/24/best-practice-how-to-ship-phpunit-configuration/)

hashTags: #BestPractice #ContinuosIntegration #phpunit #SebastianBergmann
