# basket

## Configurazione CORS Firebase Storage

Il caricamento dei PDF dalla pagina `calendario.html` richiede che il bucket Firebase Storage
consenta richieste cross-origin da `https://scamuzz.github.io`.

Il file `cors.json` contiene la regola CORS necessaria. Va applicata **una volta sola** tramite
Google Cloud SDK (`gsutil`):

```bash
# Installa Google Cloud SDK se non ce l'hai già:
# https://cloud.google.com/sdk/docs/install

# Autenticati con l'account Google che gestisce il progetto Firebase
gcloud auth login

# Applica la configurazione CORS al bucket
gsutil cors set cors.json gs://lista-spesa-b9eb1.firebasestorage.app
```

Dopo aver eseguito il comando, il caricamento dei PDF funzionerà correttamente.