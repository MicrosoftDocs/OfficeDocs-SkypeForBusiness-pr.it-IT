---
title: "Amministratori Configurare le impostazioni di Skype for Business online per singoli utenti"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836

description: "Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. "
---

# Amministratori: Configurare le impostazioni di Skype for Business online per singoli utenti

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](77b26eac-8228-4161-ba9f-733b187bd836.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/77b26eac-8228-4161-ba9f-733b187bd836). 
  
In questo articolo viene spiegato come amministratori configurare Skype for Business per un numero limitato di utenti. Per eseguire questa procedura in blocco, abbiamo incluso collegamenti a è possibile utilizzare i cmdlet di Windows PowerShell.
  
Per consentire (o impedire) a tutti nell'azienda di comunicare con persone esterne, vedere:
  
- [Consentire agli utenti di contattare utenti Skype for Business esterni](allow-users-to-contact-external-skype-for-business-users.md) : è possibile permettere all'organizzazione di usare le funzionalità avanzate di Skype for Business (condivisione desktop, ricerca di utenti online) per comunicare con persone in una specifica azienda attendibile (federata). Inoltre spiega come bloccare le comunicazioni con domini specifici.
    
- [Consenti agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md) . È possibile permettere alla propria organizzazione di usare Skype for Business per cercare e inviare messaggi istantanei a persone che usano l'app gratuita Skype.
    
## Configurare le impostazioni generali per un utente
<a name="__toc325019204"> </a>

È necessario disporre di [Informazioni sui ruoli di amministratore di Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) per eseguire questa procedura.
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Scegliere **Interfacce di amministrazione** > **Skype for Business**. 
    
3. Scegliere **Utenti**. 
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Scegliere quali utenti modificare. 
    
5. Nel riquadro destro scegliere **Modifica**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Nella pagina delle opzioni **Generale** selezionare o deselezionare la casella di controllo accanto alle funzionalità da modificare e quindi scegliere **Salva**.
    
|**Opzione**|**Dettagli**|
|:-----|:-----|
|Audio e video HD  <br/> |Consentire a questa persona di registrare riunioni audio, riunioni audio e video o non consentire di programmare riunioni (nessuna).  <br/> |
|Registra conversazioni e riunioni  <br/> |Scegliere cosa è consentito registrare a questa persona.  <br/> Questa opzione non è disponibile con Skype for Business Basic.  <br/> |
|Per conformità, disattivare le funzionalità non archiviate  <br/> | Scegliere questa opzione se la conservazione delle informazioni archiviate elettronicamente è un requisito di legge. <br/>  Se si seleziona questa opzione vengono disattivate le funzionalità acquisite quando si dispone di un[Posto](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) configurato nell'interfaccia di amministrazione di Exchange. Disattivate le caratteristiche seguenti: <br/>  Trasferimento di file tramite messaggistica istantanea <br/>  Pagine condivise di OneNote <br/>  Annotazioni di PowerPoint <br/> |
   
Per configurare queste impostazioni in blocco, utilizzare PowerShell. Vedere [i criteri di gestione di Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).
  
## Bloccare le comunicazioni esterne
<a name="__toc325019206"> </a>

Dopo aver [Consenti agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md) per tutti nell'azienda, è possibile bloccare selettivamente le comunicazioni esterne per persone specifiche seguendo queste istruzioni.
  
1. Scegliere **utenti**, selezionare gli utenti per cui si desidera disattivare le impostazioni e quindi scegliere **Modifica**![Modifica](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Fare clic su **Comunicazioni esterne** e deselezionare le opzioni, a seconda delle necessità:
    
  - **Skype esterni per gli utenti aziendali**: deselezionare questa casella se non si vuole che l'utente la possibilità di comunicare con gli utenti Skype for Business in domini federati.
    
  - **Gli utenti esterni Skype**: deselezionare questa casella se non si vuole all'utente di essere in grado di comunicare con persone che usano l'app gratuitaSkype.
    
3. Fare clic su **Salva**.
    
Per configurare queste impostazioni in blocco, utilizzare PowerShell. Vedere [gestire le comunicazioni in Skype for Business Online con esterno utenti e organizzazioni](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).
  
## Modificare le impostazioni di conferenze audio per un utente
<a name="__toc314837483"> </a>

1. Scegliere **utenti**, selezionare l'utente di cui si desidera per modificare, le impostazioni di conferenze audio e quindi scegliere **Modifica**![Modifica](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Scegliere **conferenze Audio**, selezionare il proprio provider di conferenze audio, digitare o modificare le informazioni richieste e quindi fare clic su **Salva**.
    
|**Impostazione di conferenze audio**|**Descrizione**|
|:-----|:-----|
|**Nome del provider** <br/> |Scegliere il provider dall'elenco.  <br/> |
|**Numero a pagamento** (obbligatorio) <br/> |Per un servizi di Audioconferenza di terze parti, questi numeri di telefono sono ricevute dal provider di conferenze audio. Se l'utente sta utilizzando Microsoft come provider di conferenze audio, questi saranno i numeri che sono impostati su bridge di conferenze audio. Formattare i numeri che si desidera che vengano visualizzate in Skype for Business e Teams Microsoft convocazioni di riunione.  <br/> |
|**Numero verde** <br/> |Per un servizi di Audioconferenza di terze parti, questi numeri di telefono sono ricevute dal provider di conferenze audio. Se l'utente sta utilizzando Microsoft come provider di conferenze audio, questi saranno i numeri che sono impostati su bridge di conferenze audio. Formattare i numeri che si desidera che vengano visualizzate in Skype for Business e Teams Microsoft convocazioni di riunione.  <br/> |
|**ID conferenza e PIN** (obbligatorio) <br/> |Il partecipante PIN o una conferenza codice, utilizzato per partecipare alle riunioni pianificate da questo utente e fornite da un provider di conferenze audio di terze parti. Se l'utente sta utilizzando Microsoft come provider di conferenze audio, questo non sarà necessario.  <br/> |
   
Per configurare queste impostazioni in blocco, utilizzare PowerShell. Vedere [Impostare i numeri di telefono di conferenze Audio per organizzatori che sono presenti gli inviti di riunioni](../audio-conferencing-in-office-365/set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
## 
<a name="__toc314837483"> </a>

||
|:-----|
|![Icona breve di LinkedIn Learning.](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Nuovi utenti di Office 365?**         Vedere i corsi video gratuiti per **amministratori di Office 365 e professionisti IT**, offerti da LinkedIn Learning. |
   
## Argomenti correlati
<a name="__toc314837483"> </a>

[Configurare Skype for Business online](set-up-skype-for-business-online.md)[Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

