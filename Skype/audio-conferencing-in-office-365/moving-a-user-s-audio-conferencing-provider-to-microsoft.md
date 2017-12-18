---
title: "Spostamento di un provider di servizi di audioconferenza a Microsoft"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.PSTNConferencingEnableUsers
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 3a518241-1ecc-406a-93a1-d2653eecc0f5
description: "Change your Skype for Business users from third-party audio conferencing providers (ACP) to a Microsoft dial-in conferencing provider. "
---

# Spostamento di un provider di servizi di audioconferenza a Microsoft

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
Per usare audioconferenza in Office 365 con Skype for Business e Teams Microsoft, è necessario impostare gli utenti in esigenze dell'organizzazione per avere una licenza di ** Conferenze Audio** assegnata e il provider di conferenze audio a Microsoft. Vedere[Prova o acquista le audioconferenze in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) per ottenere ulteriori informazioni sulle licenze e sul costo.
  
## Per spostare il provider di conferenze audio di un utente a Microsoft

Se viene assegnata una licenza di **Conferenze Audio** a un utente che non dispone di un provider di conferenze audio, provider dell'utente verrà impostata automaticamente a Microsoft e non è necessario eseguire altre operazioni. Se l'utente dispone già di un provider di conferenze audio, è necessario modificare il provider dell'utente a Microsoft dopo l'assegnazione di una licenza di **Conferenze Audio**.
  
Per impostare Microsoft come provider di conferenze audio per un utente che ha una licenza di **Conferenze Audio** assegnate, ma con un altro provider di conferenze audio, procedere come segue:
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **interfaccia di amministrazione di Skype for Business**, scegli **Audioconferenza**.
    
4. Se viene visualizzato un avviso di notifica che indica che sono presenti utenti che hanno un **Audioconferenza** licenza assegnata ma non Microsoft impostato come i provider di conferenze audio ancora, fare clic **qui per spostarli**. Se non è visibile l'intestazione, in **Skype for Business admin center** fare clic su **utenti** e quindi selezionare il filtro **utenti pronti per essere spostato a conferenze Audio**.
    
5. Selezionare gli utenti che si desidera spostare e quindi nel riquadro azioni, fare clic su **Modifica**.
    
6. Selezionare **Microsoft** nell'elenco **nome Provider**.
    
    > [!NOTE]
    > Se il provider di conferenze audio di un utente viene modificato in Microsoft, le informazioni di conferenze audio dell'utente vengono modificate. Se è necessario mantenere queste informazioni, vedere record in un punto prima di modificare il provider di uno degli utenti. 
  
7. Fai clic su **Salva**.
    
## Quali altre informazioni sono necessarie?

- Se selezioni l'utente dall'elenco, puoi visualizzare le informazioni predefinite per i servizi di audioconferenza, ma non il PIN della riunione. Per reimpostare il PIN di conferenza di un utente, fai clic su **Reimposta**.
    
- Per modificare le impostazioni dei servizi di audioconferenza per un utente, seleziona l'utente dall'elenco, fai clic su **Modifica** e apporta le modifiche desiderate nella pagina **Proprietà**.
    
## Argomenti correlati

[Servizi di conferenza telefonica con accesso esterno in Office 365](../misctopics/dial-in-conferencing-in-office-365.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

