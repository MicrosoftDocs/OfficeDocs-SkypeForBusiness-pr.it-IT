---
title: "Assegnare una terza parte come provider di servizi di audioconferenza"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
description: "Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. "
---

# Assegnare una terza parte come provider di servizi di audioconferenza

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](77f68ca7-c1cf-40d9-9c23-87a6b2abe9de.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/77f68ca7-c1cf-40d9-9c23-87a6b2abe9de). 
  
Un provider di conferenze audio fornisce il  *bridge di conferenza*  . Il bridge di conferenza fornisce il numero di telefono di accesso esterno, pin e conferenza ID per le riunioni che vengono creati. È sufficiente assegnare un provider di conferenze audio agli utenti che si desidera pianificare o un cliente potenziale Skype for Business o riunioni Teams Microsoft.
  
> [!NOTE]
> Per i Microsoft Teams, un utente non è possibile utilizzare un provider di conferenze audio di terze parti, utilizzano audioconferenza in Office 365, che consente di impostare il provider di conferenze audio a Microsoft. 
  
## Procedura da eseguire PRIMA di assegnare una terza parte come provider di servizi di audioconferenza

1. A seconda del piano di Office 365, potrebbe essere necessario acquistare licenze di componente aggiuntivo per le **Conferenze Audio** per gli utenti dell'organizzazione che si desidera pianificare o un cliente potenziale di Skype per Business o Microsoft Teams riunioni usando conferenze Audio. Per ulteriori informazioni, vedere[Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. Se è stato acquistato licenze di componente aggiuntivo per le **Conferenze Audio**, assegnare agli utenti all'interno dell'organizzazione che si desidera pianificare o un cliente potenziale riunioni che utilizzano conferenze Audio. Vedere [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    > [!NOTE]
    > Se si assegna una licenza di **Conferenze Audio** a un utente **dopo** assegnarle un provider di conferenze audio di terze parti, tale persona verrà impostata automaticamente a utilizzare Microsoft come provider di conferenze audio! In questo caso, sarà necessario rimuovere prima di tutto Microsoft come provider di conferenze audio prima di assegnare un provider di conferenze audio di terze parti a tali.
  
3. Trova un provider di servizi di audioconferenza su [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530). Contattalo e informati sulla procedura per configurare i servizi.
    
    Il provider fornisce: 
    
  - **Numeri di (numero verde)** e, se sono disponibili numeri verdi.
    
  - **ID conferenza** utilizzati per ogni utente che pianifica riunioni. Gli ID conferenza sono chiamati "passcode" da alcuni provider di servizi di audioconferenza.
    
    > [!NOTE]
    > Se è stato fatto iniziale impostata per un servizi di Audioconferenza di terze parti, ma è possibile apportare modifiche, nella parte inferiore della pagina **Bridge Microsoft** **fare clic qui per configurare un provider di conferenze audio di terze parti**. 
  
    > [!NOTE]
    > Quando si abilita una persona per le conferenze audio e assegnarle un provider di conferenze audio di terze parti, i numeri di audio e gli ID conferenza (passcode) vengono aggiunti automaticamente a tutte le riunioni Skype for Business online **Nuovo** creati personalmente.
  
## Come assegnare un provider di servizi di audioconferenza di terze parti a un utente

1. In **Interfaccia di amministrazione di Skype for Business**, seleziona **Utenti**. Seleziona un utente dall'elenco e fai clic su **Modifica** nel riquadro azioni.
    
2. Nella pagina delle proprietà dell'utente, fare clic su **conferenze Audio** e immettere le informazioni:
    
  - **Nome del provider** Scegli il provider di terza parte dall'elenco.
    
  - **Numero a pagamento predefinito** È necessario.
    
  - **Numero verde predefinito** Questa operazione non è necessario.
    
  - **ID conferenza** Viene fornito dal provider di conferenze audio.
    
3. Fare clic su **Salva**.
    
4. Inviare a ogni persona il PIN ricevuto dal provider di conferenze audio. Il PIN potrebbe essere necessario accedere come l'organizzatore di una conferenza telefonica o un carattere di riempimento.
    
    > [!NOTE]
    > Quando utilizzi una terza parte come provider di servizi di audioconferenza, non puoi visualizzare o impostare i PIN per conto degli organizzatori delle riunioni. 
  
## Come assegnare una terza parte come provider di servizi di audioconferenza contemporaneamente a più utenti

1. In **Interfaccia di amministrazione di Skype for Business**, scegliere **conferenze Audio** > **bridge Microsoft**. Nella parte inferiore della pagina, fare clic sul collegamento **che si desidera configurare un provider di conferenze audio di terze parti, fare clic qui**.
    
    > [!NOTE]
    > Se è stato fatto iniziale impostata per un servizi di Audioconferenza di terze parti, ma è possibile apportare modifiche, nella parte inferiore della pagina **Bridge Microsoft** **fare clic qui per configurare un provider di conferenze audio di terze parti**. 
  
2. Nella pagina **Configura una terza parte del provider di conferenze audio**, in **gli utenti di importazione / esportazione**, fare clic su **Esportazione guidata** e quindi seguire le istruzioni della **procedura guidata Esporta utenti**. Al termine, è necessario un file che elenca gli utenti che si desidera configurare per le conferenze audio.
    
3. Invia il file creato al provider di servizi di audioconferenza di terze parti. Il provider aggiungerà le informazioni per le audioconferenze per gli utenti selezionati e restituirà il file.
    
4. Verifica che il file restituito contenga le informazioni corrette. In alcuni casi sono stati restituiti elenchi con informazioni errate. 
    
5. In **Configura una pagina del provider di conferenze audio di terze parti**, in **gli utenti di importazione / esportazione**, fare clic su **Importazione guidata** e quindi seguire le istruzioni della **procedura guidata Importa utenti**
    
6. Invia a tutti gli utenti il PIN ricevuto dal provider di servizi di audioconferenza di terze parti. Il PIN può essere necessario per intervenire come coordinatore o organizzatore della conferenza telefonica.
    
    > [!NOTE]
    > Quando utilizzi una terza parte come provider di servizi di audioconferenza, non puoi visualizzare o impostare i PIN per conto degli organizzatori delle riunioni. 
  
## Quando utilizzare una terza parte come provider di servizi di audioconferenza

Se trovano in un paese o area geografica in cui audioconferenza in Office 365 non è disponibile, la qualità del servizio non è ideale a causa di posizione o si dispone di un contratto esistente con un provider di conferenze audio di terze parti, è consigliabile usare un audio di terze parti provider di servizi di conferenza. In caso contrario, è consigliabile utilizzare Microsoft come provider di conferenze audio.
  
## Assegnare automaticamente una terza parte come provider di servizi di audioconferenza con Windows PowerShell

- Per risparmiare tempo o automatizzare l'operazione, puoi usare il cmdlet [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851).
    
    > [!NOTE]
    > Per modificare il provider di audio da Microsoft a un provider di conferenze audio di terze parti, è necessario rimuovere Microsoft come provider di conferenze audio. Per eseguire questa operazione, utilizzare il cmdlet [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) .
  
- Per ulteriori informazioni sull'uso di Windows PowerShell, consulta [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).
    
## Altre informazioni utili

Una persona all'interno dell'organizzazione è possibile utilizzare solo un provider di conferenze audio. Per modificare il provider di conferenze audio di una persona a Microsoft, vedere [Spostamento di un provider di servizi di audioconferenza a Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) o[Assegnare Microsoft come provider di conferenze audio](assign-microsoft-as-the-audio-conferencing-provider.md).
  
## Argomenti correlati

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

