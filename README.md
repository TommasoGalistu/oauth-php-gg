Come ho creato un sistema di autenticazione OAuth con Google? Ecco come!

Il processo per implementare il login tramite Google OAuth nel mio progetto è stato semplice ma richiede una serie di passaggi precisi. Ecco una panoramica di come l'ho realizzato:

    Creazione dello scaffolding del progetto:
    Per prima cosa, ho creato la struttura del progetto utilizzando VS Code, impostando i vari file e le cartelle necessarie. Questo include anche l'integrazione dei file di configurazione per gestire le variabili ambientali.

    Registrazione nella Google API Console:
    Ho acceduto alla Google API Console (https://console.developers.google.com/), dove ho creato un nuovo progetto per ottenere le credenziali necessarie all’autenticazione tramite Google. Durante questo processo, ho creato una web application e ho configurato l'URI di reindirizzamento (Redirect URI). Una volta completata la configurazione, ho ottenuto il client ID e il client secret necessari per interagire con l'API di Google.

    Configurazione delle variabili di ambiente:
    Ho creato un file .env per gestire le variabili sensibili. All'interno di questo file ho inserito le seguenti variabili per configurare l'autenticazione:

    <?php
    $google_oauth_client_id = 'TUO_CLIENT_ID';
    $google_oauth_client_secret = 'TUO_CLIENT_SECRET';
    $google_oauth_redirect_uri = 'path/google-oauth.php';
    $google_oauth_version = 'v3';

    In questo modo, ho centralizzato la configurazione, mantenendo le informazioni sensibili al sicuro e facilmente modificabili.

    Impostazione della struttura del progetto:
    Ho quindi creato la struttura completa del progetto, includendo le rotte, i controlli, e i file di stile per gestire l’interfaccia utente. Ho importato le variabili dal file .env e ho aperto una sessione PHP per mantenere i dati dell’utente autenticato.

    Gestione dell’autenticazione con Google:
    Una volta che l'utente viene reindirizzato da Google alla mia applicazione, il parametro code viene passato come parte dell'URL. Questo parametro è essenziale per ottenere un access token, che è una chiave temporanea che consente di accedere ai dati dell'utente.

    Con il codice, ho implementato una chiamata API per ottenere l’access token di Google, e successivamente un’altra richiesta per recuperare le informazioni dell’utente, come nome e indirizzo email. Queste informazioni vengono quindi salvate nella sessione per mantenerne l’autenticazione durante la navigazione.

    Redirect e visualizzazione del profilo:
    Se l'utente è correttamente autenticato, viene reindirizzato alla pagina profile.php, dove vengono mostrati i suoi dati recuperati da Google. Se il parametro code non è presente, l’utente viene inviato direttamente alla pagina di login di Google per avviare il processo di autenticazione.

Funzionamento dell'App

    Se l'utente è già autenticato, accede direttamente alla pagina profile.php.
    Se l’utente non è ancora autenticato, viene reindirizzato alla pagina di login di Google per iniziare il processo di autenticazione.
    Una volta completata l'autenticazione, l’utente viene riportato nella mia applicazione e visualizza i propri dati provenienti da Google.

Prova il login online
Se vuoi vedere il sistema di autenticazione in azione, prova a fare il login con Google direttamente sulla pagina online del progetto:
Login con Google

Con questa implementazione, ho imparato a integrare efficacemente l'autenticazione OAuth di Google in un'applicazione web, usando una combinazione di PHP, Google APIs, e gestione avanzata delle sessioni utente.