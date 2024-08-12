# Userverwaltung und Bestellhistorie

Das Ziel dieser Übung ist es das bisher gelernte Wissen zu reaktivieren. Für diese Übung benötigt ihr viele der vor den Ferien gelernten Techniken.
In der Aufgabe selbst geht es darum User und deren Einkäufe in einer JSON Datei zu speichern und zu verwalten. Diese JSON-Datei nutzen wir ale simple Lokale Datenbank.

## Hinweise

- Nutze readline-sync nur in der `index.js`
- Task 1-3 sind ausgelagerte Funktionen, die wir als erstes aufsetzen und testen

## Aufgaben

1. In der `package.json` siehst du welche Programme bereits vorinstalliert sind.

   - nodemon
   - readline-sync
     Schaue nach ob es in der `package.json` ein vor gefertigtes script gibt, falls nicht lege eines an, das nodemon verwendet. Beispiele: `npm run dev`, `npm start`, `npm run devStart`

2. Bearbeite im Ordner `modules` die vorliegenden Tasks 1-3, alle Infos dazu stehen in den `task-X.js` Dateien. <span style="color: red;">Innerhalb der Tasks arbeite **NICHT** mit readline-sync!</span>

Nachdem die drei Funktionen (Task 1-3) in der Console das richtige Ergebnis ausgeben (Expected Output in Tasks) geht es weiter mit den Hauptaufgaben.

3. Arbeite nun in der `index.js`. Sorge dafür, dass du die Funktionen aus jeder Task in der `index.js` verwenden/aufrufen kannst (import/export)

   ```js
      const outputTask1 = createUser(a, b, c...)
   ```

4. Nutze nun das FileSystem um den Output von Task 1 in der `userData.json` zu speichern

Da neue User sich nun registrieren können, kümmern wir uns nun um die Historie der getätigten Einkäufe.

5. Überprüfe ob ein Nutzer bereits in der `userData.json` vorhanden ist oder ob dieser angelegt werden muss.

6. Bei einem Einkauf suche den User, in der `userData.json`, anhand seiner Emailadresse, füge die Daten, aus Task 3, hinzu und gebe den kompletten User in der Console aus.

Expected Output:

```js
{
   "id": 1,
   "fullname": "John Doe",
   "email": "JohnDoe@mail.com",
   "password": "abc123!",
   "orderList": [
      {
         "orderId": 1,
         "date": "2024-01-01",
         "total": 8.36,
         "orderItems": [
            {
               "id": 1,
               "title": "Brot",
               "price": 1.19,
               "quantity": 2
            },
            {
               "id": 2,
               "title": "Käse",
               "price": 2.99,
               "quantity": 2
            }
         ]
      }
   ]
}
```

## Bonus

- Baue ein Interface mit readline-sync auf, damit User datein eingeben können

  - register userData
  - buy items

- Sorge dafür, dass neue User bei der Registrierung als neuer Eintrag in der `userData.json` gespeichert werden

- Speichere das UserObj wieder in der `userData.json` und überschreibe, damit den alten Speicherstand des UserObj.

## Benefits

Wir lernen den Umgang mit Daten so nach und nach, allerdings dauert es noch ungefähr 3 Monate bis wir mit großen Datenbanken arbeiten können. Es gibt auch sogenannte `JSON-Server`, die man als eine Frontend Datenbank nutzen kann. Daher lernen wir hier, ein wenig den Umgang mit JSON-Dateien. Dadurch habt ihr, für kleine Projekte, die Möglichkeit euch eine Datenbank selbst zu bauen ohne dafür ein Backend oder eine große Datenbank einrichten zu müssen.

Seit neustem ist es ebenfalls möglich JSON-Datein direkt in NodeJS zu importieren, ohne die Verwendung des FileSystems. Allerdings ist dies noch hoch experimentell und funktioniert oft noch nicht ganz richtig, aber es wird kommen!
