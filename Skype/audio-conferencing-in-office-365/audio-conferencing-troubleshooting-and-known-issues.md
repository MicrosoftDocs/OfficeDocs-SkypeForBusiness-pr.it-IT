---
title: "Risoluzione dei problemi e problemi noti relativi ai servizi di audioconferenza"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6

description: "Get a list of known isses when using Microsoft as their dial-in conference provider, status, and some work arounds. "
---

# Risoluzione dei problemi e problemi noti relativi ai servizi di audioconferenza

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](72979911-5319-4de2-a275-4dd9a0f44fe6.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/72979911-5319-4de2-a275-4dd9a0f44fe6). 
  
 **Questo articolo è rivolto ai clienti Skype for Business e Microsoft Teams che usano Microsoft come provider per audioconferenze. Non interessa i clienti che usano provider per audioconferenze di terzi (ACP).**
  
## Risoluzione dei problemi e problemi noti

Conferenze audio che viene utilizzato Microsoft come provider di conferenze audio ha problemi correnti che sono stati revisioni e attivamente esaminati e verranno risolto potenzialmente quando la caratteristica viene aggiornata in futuro versioni di Office 365.
  
Per risolvere potenziali problemi durante la configurazione e il funzionamento dei servizi di audioconferenza per gli utenti dell'organizzazione che usano le app Skype for Business o Microsoft Teams, fai riferimento al presente articolo.
  
### App Microsoft Teams

|**Problema**|**Comportamento/sintomi**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|I chiamanti PSTN con lo stesso "numero da" vengono visualizzati come lo stesso utente in un elenco dei partecipanti alla riunione.  <br/> |Quando più chiamanti PSTN partecipano a una riunione e i loro ID chiamanti sono identificati come singolo numero, verranno visualizzati come un singolo chiamante nell'elenco dei partecipanti alle riunioni.  <br/> |Non ci sono soluzioni alternative.  <br/> |25/9/2017  <br/> |
|Il pannello Info riunione a volte non viene visualizzato.  <br/> |Il pannello Info riunione può non essere visualizzato nel client Teams quando gli utenti eseguono una ricerca per numero di telefono bridge conferenze o ID conferenze.  <br/> |Consultare i dettagli della riunione o il calendario di Outlook per vedere il numero di telefono bridge conferenza o l'ID conferenza.  <br/> |25/9/2017  <br/> |
|Gli inviti alle riunioni per il componente aggiuntivo Outlook mostrano caratteri senza significato per le coordinate PSTN per le localizzazioni diverse da US.  <br/> |Quando si programmano riunioni private con il componente aggiuntivo Outlook per Microsoft Teams in computer con localizzazione non US, le coordinate PSTN possono contenere caratteri senza significato.  <br/> |Non ci sono soluzioni alternative.  <br/> |25/9/2017  <br/> |
|Chiamata esterna è necessario utilizzare 5 cifre o più.  <br/> |Gli utenti si tenta di effettuare chiamate in uscita da una riunione devono digitare 5 o più cifre, anche se è disponibile per normalizzare composizione cifra breve a e. 164 dial plan normalizzazione regola.  <br/> |Effettuare la chiamata con il numero DID o locale completo invece del numero interno.  <br/> |25/9/2017  <br/> |
|Il controllo per le chiamate esterne a volte non viene visualizzato.  <br/> |Il controllo per le chiamate esterne può non essere visibile nel pannello Info riunione.  <br/> |Non ci sono soluzioni alternative.  <br/> |25/9/2017  <br/> |
|ID conferenza statico non sono supportati per le riunioni Teams Microsoft.  <br/> |Se l'amministratore esegue l'override l'impostazione predefinita ID conferenza dinamici per ID conferenza statica, questa impostazione non ha effetto per le riunioni Teams Microsoft. Vedere [Utilizzo degli ID dinamici di conferenze Audio all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |Non ci sono soluzioni alternative.  <br/> |25/9/2017  <br/> |
   
### App Skype for Business

|**Problema**|**Comportamento/sintomi**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Le notifiche di entrata o uscita siano attivate quando si avvia una riunione, ma si disattivarli subito dopo l'inizio della riunione.  <br/> |Per impostazione predefinita, le notifiche di entrata o uscita sono disabilitate per le riunioni in cui i partecipanti partecipare da entrambe Skype per le aziende: App e quando accedono tramite telefono. È possibile abilitare gli annunci nelle **Opzioni della riunione Skype** di Skype per Business app. Per una riunione in cui tutti i partecipanti accedono e partecipare a una riunione, sono abilitate le notifiche di entrata o uscita per impostazione predefinita, come l'elenco dei partecipanti non è disponibile per tutti i partecipanti. Quando una riunione è stato avviato con solo i partecipanti alla chiamata nella voce e attivate le notifiche di uscita, ma quando un join dei partecipanti usando un Skype per Business app, in modo che le notifiche disattivata. Quando disattivata, le notifiche per attivare nuovamente utilizzando le **Opzioni di riunione Skype** in di Skype per Business app. <br/> |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|Se un utente viene eseguito il provisioning la prima volta, che viene assegnata una licenza E5, potrebbe essere possibile per la posta elettronica di benvenuto di conferenze Audio per non essere recapitati all'utente se non è abilitata la cassetta postale.  <br/> |In questo caso, è sempre possibile inviare di nuovo le informazioni di conferenze audio dell'utente usando **conferenze Audio** in di Skype per Business admin center o tramite PowerShell. Vedere[Attivare o disattivare i messaggi di posta elettronica invio quando modificate le impostazioni di conferenze Audio](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md).  <br/> > [!NOTE]> Per inviare di nuovo il PIN della conferenza audio all'utente, deve reimpostare il PIN. Questa può essere eseguita anche utilizzando **conferenze Audio** in Skype for Business admin center oppure tramite PowerShell.          |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|La visualizzazione delle chiamate per i servizi di audioconferenza nei rapporti sull'utilizzo può richiedere fino a 24 ore.  <br/> |Siamo alla ricerca in avanti per apportare miglioramenti in quest ' area negli aggiornamenti futuri del servizio.  <br/> |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|Quando un chiamante accede a un bridge di conferenza dopo la riunione è stata bloccata da un utente Skype for Business, in non è presente una notifica nella finestra di app Skype for Business conferma che l'utente è in attesa nella sala di attesa.  <br/> |Si tratta di un'impostazione inerente alla progettazione; tuttavia, alla luce dei feedback raccolti, abbiamo deciso di introdurre un supporto per questa funzionalità nei prossimi aggiornamenti del servizio.  <br/> |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
   
## Argomenti correlati

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

