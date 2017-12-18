---
title: "Numeri di telefono per i servizi di audioconferenza"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- LIL_Placement
- Strat_SB_PSTN
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7

description: "Learn what countries and regions have dial-in conferencing numbers, and how they are automatically assigned."
---

# Numeri di telefono per i servizi di audioconferenza

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
Quando configuri i servizi di **audioconferenza** in Skype for Business e Microsoft Teams, all'organizzazione vengono automaticamente assegnati dei numeri di telefono di accesso esterno. Puoi visualizzare i numeri di telefono che vengono assegnati al tuo bridge di conferenza telefonica con accesso esterno passando all' **interfaccia di amministrazione di Skype for Business** > **Servizi di audioconferenza** > **Bridge Microsoft**. Consulta [Visualizzare un elenco di numeri di conferenze Audio](see-a-list-of-audio-conferencing-numbers.md).
  
> [!NOTE]
> Non è presente una risorsa che contiene un elenco di tutti i numeri di telefono per conferenze Audio. Se si sta cercando di verificare se sono disponibili i numeri di telefono di accesso esterno nel proprio area o paese/area geografica, usare **Skype for Business admin center** > **vocali** > **Numeri di telefono**, fare clic su **Aggiungi** quindi **Nuovi numeri di servizio**. Utilizzare gli elenchi per **Paese/area geografica**, stato **/area geografica** e **città** per filtrare la ricerca.> Inoltre, se si sta cercando numeri servizio gratuito di pagamento, **numero verde** selezionare da **stato/regione** elenco.
  
## Copertura di conferenze audio e prezzi

Per un elenco completo di tutti i paesi/aree geografiche e città in cui conferenze Audio è disponibile, vedere [Le conferenze PSTN con relativi numeri di telefono sono disponibili nel mio Paese o nella mia area geografica?](https://support.office.com/article/1096d81e-7e14-488c-95d8-b8322e39c059).
  
[Prezzi per le conferenze Audio](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)
  
## Numeri di telefono di accesso esterno nell'invito alla riunione

Quando Skype for Business Online o Microsoft Teams utente pianifica una riunione in Outlook o Outlook Web App, il numero di conferenze audio predefinito impostato per l'utente è incluso nella convocazione di riunione. Se si desidera selezionare un numero predefinito diverso per uno o più utenti, è possibile modificarlo facendo clic su **Skype for Business admin center** > **conferenze Audio** > **utenti**. Vedere [Impostare i numeri di telefono di conferenze Audio per organizzatori che sono presenti gli inviti di riunioni](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
Puoi visualizzare gli altri numeri di accesso esterno facendo clic sul collegamento **Trova un numero locale** nell'invito alla riunione.
  
## Numeri di telefono di accesso esterno impostare un bridge di conferenze audio

Esistono due tipi di numeri di telefono per conferenze audio che è possono assegnare il bridge di conferenza: **Shared** e **dedicato**. Entrambi i tipi di questi numeri possono essere usati dal qualsiasi chiamante per partecipare alle riunioni audio utilizzate all'interno dell'organizzazione.
  
 **Dedicato i numeri di telefono** sono i numeri di telefono sono disponibili solo per gli utenti dell'organizzazione. È possibile cambiare le lingue che vengono utilizzate quando si riceve una chiamata a uno di questi numeri.
  
 **I numeri di telefono condivisi** sono i numeri di telefono che possono essere condivisi con altre organizzazioni di Office 365. Non è possibile modificare le lingue che vengono utilizzate quando si riceve una chiamata a uno di questi numeri.
  
Mentre il numero di telefono per i servizi di audioconferenza predefinito che è stato assegnato a un organizzatore è riportato esclusivamente nell'invito alla riunione, un chiamante può utilizzare uno qualsiasi dei numeri assegnati al bridge di conferenza per partecipare a una riunione tramite telefono. L'elenco dei numeri utilizzabili per partecipare a una riunione tramite telefono viene visualizzato facendo clic sul collegamento **Trova un numero locale** incluso in ogni invito alla riunione.
  
## Assegnare automaticamente numeri di telefono per i servizi di audioconferenza

Condiviso telefono audioconferenza numeri vengono automaticamente assegnati alle organizzazioni quando è abilitate per le conferenze audio. Quando sono assegnati i numeri di telefono, come il numero di telefono predefinito del bridge di conferenza viene assegnato un numero di telefono. Il numero di telefono assegnato come il numero predefinito di bridge sarà dal paese/area geografica dell'organizzazione.
  
> [!NOTE]
> Il percorso paese o area geografica dell'organizzazione sono disponibili per l'accesso all'interfaccia **di amministrazione di Office 365** e la ricerca in **Profilo dell'organizzazione**. 
  
> [!CAUTION]
> A causa di disponibilità limitata dei numeri di telefono a pagamento Venezuela, dell'Indonesia e Emirati Arabi Uniti (Emirati Arabi Uniti), organizzazioni da questi paesi/aree geografiche non è presente un numero a pagamento di conferenze Audio automaticamente loro assegnato. Numeri verdi da queste posizioni disponibili a seconda dell'inventario disponibile. 
  
I numeri di telefono dedicato audioconferenza sono i numeri di servizio che è possibile aggiungere e quindi assegnare alla propria organizzazione. Sono disponibili numeri di servizio utilizzando **Skype per Business admin center**. Per informazioni dettagliate, vedere [Recupero di numeri di telefono di servizio Skype for Business](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md).
  
Per visualizzare un elenco di tali paesi/aree geografiche che hanno automaticamente assegnati numeri di telefono organizzazioni, vedere [Paesi e aree disponibilità per conferenze Audio e si chiama plan di messaggistica unificata](../countries-and-region-availability-for-audio-conferencing-and-calling-plans/countries-and-region-availability-for-audio-conferencing-and-calling-plans.md).
  
## Quali altre informazioni devi conoscere?

- Per visualizzare l'elenco delle lingue supportate per le conferenze audio, vedere [Lingue supportate da audioconferenza](audio-conferencing-supported-languages.md).
    
- Puoi usare il cmdlet [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) per visualizzare i numeri di telefono dedicati per i servizi di audioconferenza per l'organizzazione.
    
- Puoi utilizzare il cmdlet [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) per visualizzare le lingue che possono essere configurate per un numero di telefono di accesso esterno dedicato.
    
- Puoi configurare fino a 4 lingue per ogni numero di telefono dei servizi di audioconferenza, una principale e tre secondarie. Puoi anche impostare lingue in un numero di telefono dedicato per i servizi di audioconferenza.
    
- Per impostare il numero di telefono di accesso esterno per un utente, vedere [Impostare i numeri di telefono di conferenze Audio per organizzatori che sono presenti gli inviti di riunioni](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
    
||
|:-----|
|![Icona breve di LinkedIn Learning.](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Nuovi utenti di Office 365?**         Vedere i corsi video gratuiti per **amministratori di Office 365 e professionisti IT**, offerti da LinkedIn Learning. |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  
## Vedere anche
<a name="MT_Footer"> </a>

#### 

[Servizi di conferenza telefonica con accesso esterno in Office 365](../misctopics/dial-in-conferencing-in-office-365.md)

