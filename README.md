# Implementacja generatora haseł

## API dla generatora haseł

W repozytorium https://github.com/dominisz/passwordgeneratorapi znajduje się API dla generatora haseł

### PasswordGeneratorService
Interfejs `PasswordGeneratorService` udostępnia dwie metody:
- `generate(PasswordGeneratorParameters)` - generuje jedno hasło na podstawie przekazanych parametrów
- `generate(PasswordGeneratorParameters, int)` - generuje wymaganą liczbę haseł na podstawie przekazanych parametrów
```
public interface PasswordGeneratorService {

    String generate(PasswordGeneratorParameters passwordGeneratorParameters);
    List<String> generate(PasswordGeneratorParameters passwordGeneratorParameters, int count);

}
```
### PasswordGeneratorParameters
Klasa `PasswordGeneratorParameters` wykorzystywana jest do przekazania informacji dla generatora o właściwościach generowanego hasła:
- `passwordLength` - wymagana długość hasła
- `includeSymbols` - czy hasło powinno zawierać symbole (np. !@#$%^&*())
- `includeLowercaseCharacters` - czy hasło powinno zawierać małe litery
- `includeUppercaseCharacters` - czy hasło powinno zawierać duże litery

```
public class PasswordGeneratorParameters {

    int passwordLength;
    boolean includeSymbols;
    boolean includeNumbers;
    boolean includeLowercaseCharacters;
    boolean includeUppercaseCharacters;

}
```
## Zadanie

Utworzyć implementację interfejsu `PasswordGeneratorService`. Utworzyć zestaw testów jednostkowych do implementacji.