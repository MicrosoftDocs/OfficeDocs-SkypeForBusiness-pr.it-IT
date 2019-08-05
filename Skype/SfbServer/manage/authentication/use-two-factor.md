---
title: Usare l'autenticazione a due fattori con client Skype for business e Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: "Riepilogo: usare l'autenticazione a due fattori con Skype for Business Server e Skype for business."
ms.openlocfilehash: 532e7567444b78dd30d053cf91aef1c10f0970bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190352"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Usare l'autenticazione a due fattori con client Skype for business e Skype for Business Server
 
**Riepilogo:** Usa l'autenticazione a due fattori con Skype for Business Server e Skype for business.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Accedere a Skype for business per la prima volta

Le informazioni di accesso vengono in genere configurate automaticamente quando si installa Skype for business. Ma la prima volta che usi Skype for business, potresti dover avviare manualmente il client.
  
### <a name="to-sign-in-for-the-first-time"></a>Per accedere per la prima volta

1. Accedere alla rete dell'organizzazione.
    
2. Selezionare **Avvia** > **tutti i programmi** > **Skype for business**.
    
    Dovrebbe essere visualizzata la schermata di accesso.
    
    - Se la casella indirizzo di accesso è già stata compilata, verificare che l'indirizzo visualizzato sia corretto.
    
    - Se non è corretto o se la casella è vuota, immettere l'indirizzo di accesso (in genere corrisponde all'indirizzo di posta elettronica).
    
    - Se viene visualizzata una casella password vuota, aggiungere la password.
    
3. Selezionare **Accedi**.
    
## <a name="sign-out-of-skype-for-business"></a>Disconnettersi da Skype for business

Dopo aver completato l'uso di Skype for business, è possibile chiudere la visualizzazione, disconnettersi dalla sessione o uscire dal programma, tutto dal menu file. La tabella seguente illustra le differenze tra le opzioni.
  
|**Opzione**|**Cosa fa**|**Come eseguirlo**|
|:-----|:-----|:-----|
|Vicino  <br/> |Chiude lo schermo ma consente di continuare a eseguire la sessione di Skype for business identificata con l'ID utente. In questo modo puoi continuare a ricevere notifiche e interagire con altri utenti. <br/> <br/> Puoi riportare lo schermo in qualsiasi momento facendo clic sull'icona Skype for business nella barra delle applicazioni o nell'area di notifica nella parte inferiore dello schermo.  <br/> | Nella finestra principale di Skype for business eseguire una delle operazioni seguenti: <br/> 1. Selezionare il pulsante **Opzioni** , quindi selezionare **file** > **Chiudi**.  <br/> 2. fare clic sul pulsante **Chiudi** (X) nell'angolo in alto a destra della finestra. <br/> |
|Disconnettersi  <br/> |Termina la sessione associata all'ID utente, ma Skype for business continua a essere eseguito in background. Quando ci si disconnette, verrà visualizzata la finestra di accesso.  <br/> **Suggerimento:** Selezionare **Elimina le informazioni** di accesso quando si esce per rimuovere il record dell'ID di accesso e della password dal computer. In questo modo, puoi semplificare la risoluzione dei problemi di accesso per il supporto delle persone. Può anche essere utile garantire che le informazioni di accesso siano più sicure, rendendo difficile per gli utenti non autorizzati l'accesso con le credenziali. <br/> |Nella finestra principale di Skype for business, selezionare il pulsante **Opzioni** , quindi selezionare **file** > **disconnettersi**.  <br/> |
|Uscita  <br/> |Termina la sessione di Skype for business e arresta Skype for business nel computer. Dopo aver terminato, se si vuole riavviare, selezionare **Avvia** > **tutti i programmi** > Skype for business. <br/> |Nella finestra principale di Skype for Business seleziona il pulsante **Opzioni** , quindi seleziona**Esci**da **file** > .  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Accedere a Skype for business con una smart card

Alcune organizzazioni usano ora un processo di accesso a più passaggi, denominato autenticazione a due fattori, per aumentare la sicurezza per gli utenti. Se si prevede di usare questa opzione, è necessaria una "smart card" per accedere a Skype for business. Le smart card possono essere fisiche o virtuali:
  
- **Fisiche** Informazioni sulle dimensioni di una carta di credito. Quando si effettua l'accesso, è possibile inserirla in un lettore di smart card.
    
- **Virtuale** Non un oggetto fisico, ma un identificatore elettronico che viene scritto in un chip speciale nel computer, che in sostanza crea la smart card nel computer. Disponibile solo per l'uso con i computer Windows 8 che contengono il chip TPM (Trusted Platform Module).
    
### <a name="enroll-your-smart-card"></a>Registrare la smart card

Prima di poter accedere con una smart card, la scheda deve essere "registrata", ovvero le credenziali utente devono essere identificate con la scheda. Questo è il caso che la carta sia fisica o virtuale. Questo processo può essere già stato eseguito dall'amministratore di Skype for Business Server. Verificare se non si è certi che sia stato fatto.
  
> [!NOTE]
> Poiché ogni smart card virtuale è associata solo al dispositivo in cui è installato, sarà necessario registrare una scheda separata per ogni computer Windows 8 usato. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Per registrare manualmente la smart card

1. Accedere al computer in cui verrà eseguito Skype for business.
    
2. Usando Internet Explorer, passare alla pagina di registrazione Web dell'autorità di certificazione dell'organizzazione. 
    
    Rivolgersi all'amministratore di Skype for Business Server per l'indirizzo Web della risorsa, se non è già disponibile. L'URL avrà un aspetto simile al seguente https://MyCA:. [NomeSocietà]. com/certsrv.
    
    > [!NOTE]
    > Se si usa Internet Explorer 10, potrebbe essere necessario visualizzare il sito Web in modalità compatibilità. 
  
3. Quando viene richiesto di accedere alla pagina certificazione, accedere con l'account di dominio (anziché come amministratore del computer).
    
4. Nella pagina di benvenuto del sito Web selezionare **Richiedi un certificato**.
    
5. Selezionare **richiesta avanzata**.
    
6. Selezionare **Crea e inviare una richiesta alla CA**, quindi fare clic su **Avanti**.
    
7. Ora verrà visualizzata una pagina denominata stazione di registrazione smart card. Approva la richiesta di installazione del controllo ActiveX e quindi compila il modulo di richiesta Advanced Certificate nel modo seguente:
    
    un. Selezionare **utente smartcard** nell'elenco a discesa **modello di certificato** .
    
    b. Selezionare **Crea nuovo set di tasti**.
    
    c. Trovare le informazioni sul produttore nell'etichetta della smart card e selezionare tale produttore nell'elenco a discesa **CSP** .
    
    3D. Selezionare **CSP** come formato di richiesta, se non è già selezionato.
    
    e. Selezionare **SHA1** nell'elenco a discesa algoritmo hash, se non è già selezionato.
    
    f. Assegnare un nome al certificato che verrà riconosciuto e quindi fare clic su **Invia**.
    
8. Inserire ora la smart card vuota nel lettore di schede collegata alla stazione di registrazione e fare clic su **registra**.
    
9. Quando richiesto, immettere il PIN (Personal Identification Number) e quindi fare clic su **OK**.
    
    > [!NOTE]
    > Se la persona del supporto tecnico non ha ricevuto un PIN speciale da usare per la registrazione della smart card, usare il valore PIN della smart card predefinito, ovvero 12345678. 
  
10. Selezionare l'opzione per forzare l'utente a cambiare il PIN per la prima volta che viene usata la smart card.
    
11. Inserire ora la smart card vuota nel lettore di schede collegata alla stazione di registrazione e fare clic su **registra**.
    
12. Quando richiesto, immettere il PIN (Personal Identification Number) e quindi fare clic su **OK**.
    
    > [!NOTE]
    > Se la persona del supporto tecnico non ha ricevuto un PIN speciale da usare per la registrazione della smart card, usare il valore PIN della smart card predefinito, ovvero 12345678. 
  
13. Selezionare l'opzione per forzare l'utente a cambiare il PIN per la prima volta che viene usata la smart card.
    
14. Fare clic su **OK** per confermare che il certificato visualizzato contiene le informazioni.
    
15. Quando viene visualizzato l'avviso che il certificato è stato emesso, fare clic su **installa questo certificato** per completare il processo di registrazione.
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Accedere a Skype for business con le credenziali della smart card

Prima di usare la smart card per la prima volta, è consigliabile fare clic su **Elimina le informazioni di accesso** nella pagina di accesso di Skype for business. In questo modo vengono cancellate le credenziali di accesso archiviate nel computer e viene eliminata una possibile origine di errore.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Per accedere a Skype for business con le credenziali della smart card

1. Avviare il client Skype for business.
    
2. Nella schermata di accesso digitare il nome dell'account utente di accesso nella casella **indirizzo di accesso** e quindi fare clic su **Accedi**.
    
3. Se si usa una smart card virtuale, ignorare questo passaggio.
    
    Se si usa una smart card fisica, inserire la smart card nel lettore di smart card e quindi fare clic su **OK** quando viene rilevata la scheda.
    
4. Digitare il PIN number per la smart card e quindi fare clic su **OK**.
    
    > [!NOTE]
    > Se il numero di PIN della smart card non è stato assegnato dalla persona di supporto, usare il valore predefinito, ovvero 12345678. 
  
## <a name="see-also"></a>Vedere anche

[Gestire l'autenticazione a due fattori in Skype for Business Server](two-factor-authentication.md)
  
[Configurare l'autenticazione a due fattori in Skype for Business Server](configure-two-factor.md)
