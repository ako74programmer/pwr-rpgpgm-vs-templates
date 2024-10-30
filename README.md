Aby stworzyć szablon programu dla języka CLLE (ILE CL) w środowisku Visual Studio Code, musisz utworzyć plik snippets. Dzięki temu można zdefiniować szybki szablon, który pozwoli na wstawienie kodu w CLLE za pomocą skrótu.

Poniżej znajdziesz prosty przykład szablonu snippet dla programu CLLE, który wypisuje komunikat do logu (tutaj możesz użyć `SNDPGMMSG` dla CLLE):

1. Wybierz **File > Preferences > Configure Snippets** i wybierz **New Snippets**.
2. Podaj nazwę clle-snippets. Skopiuj poniższy kod do nowego pliku snippetu `clle-snippets.code-snippets`:

```json
{
	"Send message to log": {
		"scope": "clle,cl,clp",
		"prefix": "sendmsg",
		"body": [
			"PGM",
			"    DCL VAR(&MSG) TYPE(*CHAR) LEN(50) VALUE('$1')",
			"    SNDPGMMSG MSG(&MSG)",
			"ENDPGM"
		],
		"description": "Send a program message in CLLE"
	}
}
```

### Wyjaśnienie:
- **"scope": "clle,cl,clp"** – szablon będzie działał w plikach z rozszerzeniem clle, cl, clp.
- **"prefix": "sendmsg"** – skrót, który wywołuje szablon (wpisz `sendmsg`, aby szybko wstawić kod).
- **"body"** – główna zawartość programu CLLE, w tym miejscu snippet umieszcza `PGM` i `ENDPGM`, deklaruje zmienną `&MSG`, i używa `SNDPGMMSG`, aby wysłać wiadomość.
- **"$1"** – po wstawieniu szablonu możesz szybko podać tekst wiadomości.

Teraz po wpisaniu `sendmsg` i naciśnięciu Tab snippet wstawi szablon dla prostego programu CLLE.