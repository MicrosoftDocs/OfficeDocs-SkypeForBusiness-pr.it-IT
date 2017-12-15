---
title: "Configurare le audioconferenze per Skype for Business e Microsoft Teams"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365P_DialInConfDesc
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
- Strat_SB_PSTN
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9

description: "Learn how to set up dial-in or audio conferencing (PSTN Conferencing) for the people in your business who need to join conference calls using a phone. "
---

# Configurare le audioconferenze per Skype for Business e Microsoft Teams

Talvolta le persone all'interno dell'organizzazione dovranno usare un telefono per accedere a una riunione. Skype for Business e Microsoft Teams offrono la funzione di audioconferenza proprio per queste evenienze! Le persone possono accedere alle riunioni di Skype for Business e Microsoft Teams usando un telefono, al posto di usare la app di Skype for Business o Microsoft Teams su un dispositivo mobile o PC.
  
Devi solo impostare l'audioconferenza per chi prevede di programmare o condurre le riunioni. I partecipanti alle riunioni che non chiamano la riunione non hanno bisogno di licenze assegnate o altre configurazioni. 
  
Per le domande frequenti sulle audioconferenze, consulta [Audio Conferencing common questions](audio-conferencing-common-questions.md).
  
## Passaggio 1: acquisto e assegnazione delle licenze
<a name="__top"> </a>

Per eseguire questo passaggio, è necessario essere un [Informazioni sui ruoli di amministratore di Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d). 
  
1. Scopri se le audioconferenze di Office 365 sono disponibili nel tuo Paese o area geografica. Consulta questo [Paesi e aree disponibilità per conferenze Audio e si chiama plan di messaggistica unificata](../countries-and-region-availability-for-audio-conferencing-and-calling-plans/countries-and-region-availability-for-audio-conferencing-and-calling-plans.md). 
    
2. Consulta informazioni sulle licenze da acquistare per i servizi di audioconferenza e sul loro costo, consulta [Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) e acquista le licenze.
    
3. [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) acquistate agli utenti dell'organizzazione che intendono pianificare o condurre riunioni.
    
4. Se hai acquistato licenze per i componenti aggiuntivi di **Audioconferenza** e licenze di Crediti comunicazioni, assegna anche queste licenze. Per avere istruzioni, vedi[Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
## Passaggio 2: scelta del provider di servizi di audioconferenza
<a name="__top"> </a>

Un provider di servizi di audioconferenza fornisce un  *bridge per audioconferenza*  . Il bridge di conferenza configura i numeri di telefono per accesso esterno, i PIN e gli ID conferenza per le riunioni. Scegli se usare Microsoft o un provider terzo di audioconferenza.
  
> [!NOTE]
> Gli utenti di Microsoft Teams non possono utilizzare un provider di servizi di audioconferenza di terze parti. 
  
- **Microsoft come provider di servizi di audioconferenza**: Per la soluzione di audioconferenza più semplice, scegli Microsoft come provider.
    
- **Un soggetto terzo come provider di audioconferenza**: Se ti trovi in un paese in cui l'audioconferenza di Office 365 non è disponibile, la qualità del servizio non è granché a causa della posizione oppure hai un contratto in essere, scegli un provider terzo di audioconferenza. Per trovare un provider, accedi a **[Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530)**.
    
> [!TIP]
> Gli utenti dell'organizzazione possono utilizzare sia Microsoft sia una terza parte come provider di servizi di audioconferenza. In questo caso, tuttavia, la configurazione e la gestione delle audioconferenze è più complessa. 
  
Per un confronto dettagliato tra Microsoft come provider di audioconferenza e una terza parte, consulta [Confronto tra provider di conferenze audio](compare-audio-conferencing-providers.md). 
  
## Passaggio 3: assegnare il provider di servizi di audioconferenza alle persone che conducono o pianificano le riunioni
<a name="__top"> </a>

Ora che hai deciso il provider di servizi di audioconferenza, devi assegnare il provider alle persone nella tua organizzazione che conducono o pianificano le riunioni. Scegli una delle opzioni seguenti: 
  
- [Assegnare Microsoft come provider di conferenze audio](assign-microsoft-as-the-audio-conferencing-provider.md) .
    
- [Assegnare una terza parte come provider di servizi di audioconferenza](assign-a-third-party-as-the-audio-conferencing-provider.md) .
    
## Passaggio 4: configurare le convocazioni di riunione
<a name="__top"> </a>

I passaggi seguenti sono **facoltativi**, ma molti amministratori preferiscono eseguirli.
  
1. [Personalizzare inviti alle riunioni](../set-up-skype-for-business-online/customize-meeting-invitations.md) . I numeri telefonici di accesso esterno impostati per l'utente vengono aggiunti automaticamente alle convocazioni di riunione inviate ai partecipanti. Tuttavia, puoi aggiungere collegamenti a istruzioni e informative legali, un messaggio di testo e un piccolo logo aziendale.
    
2. [Impostare i numeri di telefono di conferenze Audio per organizzatori che sono presenti gli inviti di riunioni](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md) . Si tratta del numero di telefono visualizzato nella riunione che è stata pianificata dall'utente.
    
3. [Impostazione delle lingue dell'operatore automatico per le conferenze Audio](set-auto-attendant-languages-for-audio-conferencing.md) delle audioconferenze con cui accogliere un chiamante quando si collega a un'audioconferenza. Questo passaggio si applica solo se usi Microsoft come provider di audioconferenza.
    
4. [Impostare la lunghezza del PIN per le riunioni di conferenze Audio](set-the-length-of-the-pin-for-audio-conferencing-meetings.md) .
    
> [!NOTE]
> Questa funzione non è ancora disponibile per i clienti che usano Office 365 con operatore 21Vianet in Cina. Per saperne di più, consulta [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE). 
  
||
|:-----|
|![Icona breve di LinkedIn Learning.](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Nuovi utenti di Office 365?**         Vedere i corsi video gratuiti per **amministratori di Office 365 e professionisti IT**, offerti da LinkedIn Learning. |
   
## Vedere anche
<a name="__top"> </a>

#### 

[Audio Conferencing common questions](audio-conferencing-common-questions.md)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Numeri di telefono per i servizi di audioconferenza](phone-numbers-for-audio-conferencing.md)
  
[Impostare le opzioni per riunioni online e conferenze telefoniche](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)

