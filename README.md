# Maria-e-Ykaro-API

Um API de procura de produtos.
Para pesquisar a marca “maybelline”, acrescente 'brand=maybelline'. Por exemplo:
http://makeup-api.herokuapp.com/api/v1/products.json?brand=maybelline
Para pesquisar os “batons” da marca “covergirl”, você acrescentaria 'brand=covergirl' e '&product_type=lipstick'. Por exemplo:
http://makeup-api.herokuapp.com/api/v1/products.json?brand=covergirl&product_type=lipstick








const http = require('http');

const searchParameter = product/[NOME_DO_PRODUTO].json   // Parâmetro de busca

const options = {
  hostname: http://makeup-api.herokuapp.com/api/v1/products.json ,
  path: '/search?query=' + encodeURIComponent(searchParameter),
  method: 'GET'
};

const req = http.request(options, (res) => {
  let nome = '';

  res.on('nome', (chunk) => {
    nome += chunk;
  });

  res.on('end', () => {
    console.log(nome);  
  });
});

req.on('error', (error) => {
  console.error('Erro na requisição:', error);
});

req.end();
