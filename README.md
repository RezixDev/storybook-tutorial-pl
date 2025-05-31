# Storybook Tutorial PL
Storybook Tutorial, Po co? Dlaczego?

Szukając informacji w internecie, często natrafiałem na informację, bądź komentarze użytkowników, że Storybook nie jest potrzebny. Że jest to jedynie Overhead i po co tracić na niego czas.

Więc... czy jest tobie potrzebny Storybook? Bo jak wiele rzeczy w programowaniu...

## To zależy

Jeżeli budujesz małą aplikację sam i wiesz co istnieje w aplikacji (w końcu te komponenty sam napisałeś), wiesz jak one wyglądają i nie masz skomplikowanego Backendu z API, to prawdopodobnie nie będziesz potrzebował Storybooka. 

Jeżeli natomiast tworzysz projekt w grupie z innymi ludźmi, który jest podzielony na zespół Backend/Frontend i istnieją osoby, które chcą zobaczyć jak wyglądają pojedyńcze komponenty, bez konieczności startowania aplikacji, to jest to sytuacja, gdzie Storybook wydaje się być dobrym rozwiązaniem. 

Dodatkowym plusem Storybooka jest to, że Frontend i Backend jest w stanie w pełni niezależnie od siebie pracować.

Jeżeli Backend nie nadąża z dostarczaniem Endpointów API, bądź logika domenowa nie jest do końca jasna, to Frontend jest w stanie tworzyć i testować Designy niezależnie od tego co dostarcza Backend.

## Mock-Upy

Są to dane "testowe", które nie pochodzą bezpośrednio z bazy danych, a definiują one jedynie potencjalne dane, które mogą w przyszłosci pochodzić z Backendu. Są one bardzo pomocne, bo możemy przetestować jak nasze elementy UI się będą zachowywać bez konieczności posiadania Backendu.

## Wady Storybooka

### Upgrade Wersji

Regularne zmiany w paczkach i wymóg co jakiś czas poprawiania Configu. Nie jest to konieczność, ale lepiej jest co jakiś czas dostosować projekt do nowszej wersji. 

Na czas pisania tego Tutoriala wyszła wersja 9 (Czerwiec 2025)
https://storybook.js.org/releases/9.0

W takim przypadku trzeba sprawdzić migration guide i na podstawie jego poprawić to co zmienili.
https://github.com/storybookjs/storybook/blob/next/MIGRATION.md

Często są to Pluginy, które istniały jako paczki (npm) i które albo trafiły do Core, ze względu dużej popularności, bądź zostały zastąpione przez inny plugin jak Test runner, który został zastąpiony Vitestem: 
https://storybook.js.org/docs/writing-tests/integrations/test-runner
=> https://storybook.js.org/docs/writing-tests/integrations/vitest-addon

### Konieczność pisania Stories i aktualizacji ich

Użyteczność Storybook'a w projekcie jest tak duża jak gotowość programistów do zajmowania się nim. 
Czyli tak samo jak z testami. 

Jeżeli programiści będą je regularnie pisać i aktualizować, to jest to użyteczne narzędzie, które może przyspieszyć rozwój projektu. Szczególnie, jeżeli Projekt po jakimś czas urośnie do dużych rozmiarów. 

Musi być w zespole stworzona kultura, która oczekuje od programistów tego typu praktyk. 
Bez takiej kultury, będzie ciężko wdrożyć takie rozwiązania. 

### Werdykt

Wydaje mi się, że mimo wszystko Storybook to super narzędzie pozwalające szybciej wyłapać możliwe błędy i przyspieszyć pracę zespołu, przez możliwość niezależnego rozwijania elementów projektu. 

# Instalcja

Jak zainstalować Storybooka znajdziecie tutaj:
https://storybook.js.org/docs

Aktualnie wspiera on naprawdę sporo różnych technologii, a integracja go w wasz projekt nie powinna sprawić wam zbyt dużego problemu.

Na przykładzie Reacta, istnieją dwa sposoby:
Automatyczna instalacja, czyli jest to po prostu odpalenie CLI i przejście przez wszystkie kroki:

```
npm create storybook@latest
```

Drugi sposób to manualna instalacja, gdzie instalujemy poza Core Storybook'a, dodatkową paczkę pod naszego frameworka. 
W naszym przypadku jest to React:
```
npm install --save-dev @storybook/react-vite
```


## Tworzenie Stories z AI

Dzięki Modelom LLM tworzenie Stories stało się o wiele prostsze i mogą one nam wygenerować wiele kodu Boilerplate, jednakże trzeba uważać i sprawdzać generacje.

Nie zawsze są one poprawne, gdyż mogą bazować na starszych wersjach, starszej składni, bądź generować Stories w błędnym formacie.

Na dzień dzisiejszy jesteśmy w stanie pisać Stories w naprawdę wielu formatach.
https://storybook.js.org/docs/writing-stories

Są to między innymi: js, jsx, mjs, ts, tsx, md, mdx.

I każdy format może posiadać inną formę w zależności od wybranego języka i frameworka, w którym osadziliśmy naszego Storybooka. 

Dlatego zanim zaczniemy promptować, warto sprawdzić format na który się zdecydowaliśmy (w moim przypadku .tsx) oraz  składnię jak potencjalnie wyglądałyby nasze stories.

Przykładowym promptem może być:

```
create Story in tsx format for this component:
<tutaj podajecie wasz komponent, np: Reacta>
```

W moim doświadczeniu Claude 4 oraz DeepSeek generuje je najlepiej, natomiast ChatGPT 4o stara się więcej podpowiedzieć, jak napisać Story, niż stworzyć gotowy komponent. 



