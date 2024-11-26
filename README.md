Vuoi sapere come ho fatto a creare un Oauth con google?? Semplice...

Ho creato lo scafolding del progetto.

Ho creato e compilato i dati richiesti da google Api Console
https://console.developers.google.com/

Alla fine della creazione della web application ho preso il client id e 

Su VsCode ho creato la struttura del progetto con i vari style

Ho importato le variabili dal file env e ho aperto la sessione

Ho scritto il codice gestisce l'autenticazione dell'utente tramite Google. Quando l'utente viene reindirizzato alla pagina con un parametro code (fornito da Google dopo l'autenticazione), il codice utilizza questo code per richiedere un access token. Questo token è una chiave temporanea che consente all'app di accedere ai dati dell'utente.

Dopo aver ricevuto il token, il codice invia un'altra richiesta per ottenere le informazioni dell'utente, come nome ed e-mail. Se queste informazioni vengono recuperate correttamente, vengono salvate nella sessione dell'utente per mantenerlo autenticato. Infine, l'utente viene reindirizzato alla pagina del profilo.

Se non è presente un parametro code, l'utente viene inviato alla pagina di login di Google per autenticarsi.

