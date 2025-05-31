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

Regularne zmiany w paczkach i wymóg co jakiś czas poprawiania Configu. Nie jest to konieczność, ale lepiej jest co jakiś czas dostosować projekt do nowszej wersji. 

Na czas pisania tego Tutoriala wyszła wersja 9 (Czerwiec 2025)
https://storybook.js.org/releases/9.0

W takim przypadku trzeba sprawdzić migration guide i na podstawie jego poprawić to co zmienili.
https://github.com/storybookjs/storybook/blob/next/MIGRATION.md

Często są to Pluginy, które istniały jako paczki (npm) i które albo trafiły do Core, ze względu dużej popularności, bądź zostały zastąpione przez inny plugin jak Test runner, który został zastąpiony Vitestem: https://storybook.js.org/docs/writing-tests/integrations/test-runner



