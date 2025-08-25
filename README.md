function processaTexto(texto) {
    let palavras = texto.split(/\P{L}+/u);
    const frequencias = contaFrequencias(palavras);
    let ordenadas = Object.keys(frequencias).sort(ordenaPalavra);

    function ordenaPalavra(p1, p2) {
        return frequencias[p2] - frequencias[p1];
    }

    console.log(ordenadas);
    return ordenadas.slice(0, 10);
}

function contaFrequencias(palavras) {
    let frequencias = {};
    for (let i of palavras) {
        frequencias[i] = 0;
@@ -22,8 +33,5 @@ function processaTexto(texto) {
            }
        }
    }

    console.log(frequencias);

    return palavras;
    return frequencias;
}
