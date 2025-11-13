# FixMatch

Esse projeto é uma implementação simples do método FixMatch pra fazer aprendizado semi-supervisionado no CIFAR-10. A ideia é treinar o modelo com poucos rótulos por classe e usar pseudo-rótulos pra melhorar o aprendizado nos dados não rotulados.

## Pré instalação:

Garanta que tenha python instalado e git.

No cmd, rode:

```bash
git clone https://github.com/kalebemaiaa/FixMatch.git
```

navegue para a pasta, crie uma venv (opcionalemnte) e instale as depêndencias
```bash
cd FixMatch
python -m venv venv
.\venv\Scripts\activate # windows, para linux: source venv/bin/activate
```

por fim, basta executar o script normalmente: `python (dl)_assignment_3.py`. Ele contem um exemplo de teste **alterável**, basta mudar os args.

## Como usar

Pra rodar o treinamento principal, é só chamar a `main` passando os argumentos num dicionário. Um exemplo que usei foi esse:

```python
if __name__ == "__main__":
    # @ 400 rótulo por classe
    args = {
        "data_root": "./data",
        "save_dir": "./experiments/fixmatch_cifar10_400labels",
        "label_count": 400,
        "extra_thresholds": [0.8, 0.9],
        "epochs": 27,
        "batch_size": 64,
        "mu": 7,
        "lambda_u": 1.0,
        "threshold": 0.95,
        "seed": 17
    }

    main(args)
```

## Notas

para produzir as figuras, use o history armazenado e plot com base no que foi salvo.

link vídeo relatório: ...

link_pdf_relatório: ...
