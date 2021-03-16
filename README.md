O módulo foi desenvolvido na versão Magento 2.3.6

A organização de pastas do módulo inicia com Renato(Vendor), em seguida ParcelasAttribute que é a pasta do módulo

Dentro do módulo contém, pasta etc arquivo module.xml, com as informações do módulo e sua versão de instalaçao (os dados são armazenados na tabela setup_module)
Ainda na psta etc, existe a pasta frontend e o arquivo dentro dela, routes.xml.

Pasta Setup, onde a class InstallData, insere o novo atributo e seus valores em eav_attribute.

A pasta view/frontend/template e view/frontend/layout, contém respectivamente o override de list.phtml de catalog e attribute.phtml de view product.

Os arquivos xmls, catalog_category_view.xml e catalog_product_view.xml, fazem o reference block da área onde será exibido o conteúdo, para o template que está em view/frontend/template, fazendo assim o Override sem alteração no diretorio Vendor (caso de instalações via composer).

O por fim o arquivo registration na raiz do módulo.

Após realizar o git pull origin (branch), certifique de executar  php bin/magento module:status, certifique após o comando que em modules disable esteja aparecendo Renato_ParcelasAttribute

Em seguida, execute php bin/magento setup:upgrade 

Execute php bin/magento setup:static-content:deploy

E então php bin/magento cache:clean

Caso o módulo ainda não esteja sendo exibido como ativo, execute php bin/magento setup:di:compile


