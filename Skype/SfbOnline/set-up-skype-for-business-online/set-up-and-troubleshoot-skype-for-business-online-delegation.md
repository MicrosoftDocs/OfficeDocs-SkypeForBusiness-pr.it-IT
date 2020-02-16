---
title: Configurare le deleghe e risolvere i problemi relativi alle deleghe in Skype for Business online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Questo articolo spiega come configurare e risolvere i problemi di delega di Skype for business online. In questo articolo vengono fornite indicazioni per suggerimenti per la configurazione, procedure consigliate e procedure per la risoluzione dei problemi.
ms.openlocfilehash: 6774fe36760e6a9c53808f33f7a842d5460e0f4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010799"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurare le deleghe e risolvere i problemi relativi alle deleghe in Skype for Business online

Questo articolo spiega come configurare e risolvere i problemi di delega di Skype for business online. In questo articolo vengono fornite indicazioni per suggerimenti per la configurazione, procedure consigliate e procedure per la risoluzione dei problemi.
  
## <a name="guidelines-and-requirements"></a>Linee guida e requisiti

### <a name="guidelines-for-delegation"></a>Linee guida per la delega

La configurazione e l'ottenimento della delega per il corretto funzionamento dipende dalle seguenti linee guida:
  
- È necessario usare il client completo di Skype for business 2015 con gli aggiornamenti più recenti o con il client completo Skype for business 2016.
    
- È necessario usare il client Outlook 2013 con gli aggiornamenti più recenti o con il client Outlook 2016.
    
- Verificare che il delegante e i computer delegati dispongano di un profilo di posta di Outlook che sia il profilo principale o quello predefinito. Il profilo di posta elettronica deve contenere un solo account.
    
- Skype for business per il delegante e il delegato devono essere utenti online. Inoltre, le cassette postali di Exchange Server per ogni account devono essere entrambe online o entrambe in locale.
    
- Sia il delegante che il delegato devono usare la stessa versione principale di Outlook.
    
- Il valore dell'attributo **EnableExchangeDelegateSync** deve essere impostato su **true** nei criteri client. Puoi verificare questa impostazione eseguendo il cmdlet **Get-CsClientPolicy** nel modulo di PowerShell per Skype for business online.
    
- Sia il delegante che il delegato devono avere effettuato l'accesso a Skype for business e Outlook contemporaneamente su workstation diverse.
    
- Le cassette postali condivise non sono supportate per la delega di Skype for business online. Il motivo è che la cassetta postale condivisa non ha l'elenco di controllo di accesso (ACL) di **SendOnBehalf** .
    
### <a name="skype-for-business-client-version-support"></a>Supporto della versione client di Skype for business

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Client Basic Lync/Skype for business**| Non supportato |Non supportato
|**Skype for business 2015**|Supportati| Supportati|
|**Skype for business 2016**|Supportati| Supportati|

   
### <a name="licensing-requirements"></a>Requisiti per le licenze

**Scenario di licenze Enterprise E3**

|**Licenza**|**Client**|**Note**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype for business 2015) usato con Outlook 2013 o Outlook 2016  <br/> Skype for business 2016 usato con Outlook 2013 o Outlook 2016  <br/> |Skype for Business Basic client non supporta la delega.  <br/> Per i client Mac puoi delegare le chiamate ma non le riunioni.  <br/> |
|Enterprise E3 con Office 365 Phone System + Office 365 xCalling piano  <br/> |Lync 2013 (Skype for business 2015) usato con Outlook 2013 o Outlook 2016  <br/> Skype for business 2016 usato con Outlook 2013 o Outlook 2016  <br/> Lync per Mac 2011  <br/> |Skype for Business Basic client non supporta la delega.  <br/> Per i client Mac puoi delegare le chiamate ma non le riunioni.  <br/> |
   
**Scenario di licenze Enterprise E5**

|**Licenza**|**Client**|**Note**|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |Lync 2013 (Skype for business 2015) usato con Outlook 2013 o Outlook 2016.  <br/> Skype for business 2016 usato con Outlook 2013 o Outlook 2016  <br/> |Skype for Business Basic client non supporta la delega.  <br/> Per i client Mac puoi delegare le chiamate ma non le riunioni.  <br/> |
|Piano per le chiamate Enterprise E5 Plus Office 365  <br/> |Skype for business per Mac 2016  <br/> Lync 2013 (Skype for business 2015) usato con Outlook 2013 o Outlook 2016  <br/> Skype for business 2016 usato con Outlook 2013 o Outlook 2016  <br/> Lync per Mac 2011  <br/> |Skype for Business Basic client non supporta la delega.  <br/> Per i client Mac puoi delegare le chiamate ma non le riunioni.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Configurare e verificare la delega

Per configurare la delega di Skype for business online, eseguire le operazioni seguenti:
  
### <a name="for-windows-clients"></a>Per i client Windows

 **Scheda inoltro di chiamata**
  
1. Selezionare **** > **** opzioni > strumenti**inoltro di chiamata impostazioni**.
    
2. Selezionare **Modifica membri delegati**.
    
3. Selezionare **Aggiungi**, selezionare il delegato che si vuole aggiungere e quindi scegliere **OK**.
    
 **Scheda inoltro di chiamata**
  
1. In > Outlook selezionare**Aggiungi****accesso delegati****Impostazioni** > account **file** > .
    
2. Individuare e quindi aggiungere il nome della persona che sta per essere il delegato.
    
3. Selezionare il menu **Calendario** , quindi selezionare **Editor (in grado di leggere, creare e modificare gli elementi)**.
    
### <a name="for-mac-clients---lync"></a>Per client Mac-Lync

 **Scheda inoltro di chiamata**
  
- Se il client non ha una scheda **inoltro di chiamata** con il collegamento **modifica i membri delegati** e il delegante si trova in un computer Mac, il delegante deve accedere a un computer basato su Windows per configurare la delega. Questo perché i client Mac non possono eseguire connessioni MAPI e questo è un requisito per stabilire la delega di Skype for business da Outlook.
    
### <a name="verify-success"></a>Verificare il successo

Se il programma di installazione ha esito positivo, il delegato deve vedere l' **utente che è stato aggiunto come delegato per < nome>** messaggio e che vengono create anche le **persone che gestiscono le chiamate per** il gruppo. Il delegante deve verificare che il gruppo **delegati** sia stato creato.
  
> [!NOTE]
> Le autorizzazioni di delega vengono in genere visualizzate entro 30 minuti dal processo di configurazione. Tuttavia, questo processo può richiedere fino a 24 ore per il completamento. 
  
## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="common-issues"></a>Problemi comuni

- > **Problema 1** La voce del delegato continua a essere visualizzata nelle **persone che gestiscono le chiamate per** il gruppo dopo che il delegante ha rimosso il delegato dal client di Outlook.
    
  - > **Risoluzione 1** Nel client Skype for business fare clic con il pulsante destro del mouse sul delegato nel gruppo **delegati** e quindi scegliere **Rimuovi dal gruppo**.
    
- > **Problema 2** Dopo aver concesso l'accesso al delegato tramite il client Outlook, non viene visualizzato il messaggio di conferma né le **persone che gestiscono le chiamate per** il gruppo per il delegato.
    
  - > **Risoluzione 2** Rimuovere la delega dal client Outlook, attendere circa 15 minuti per la replica e quindi aggiungere di nuovo il delegato.
    
### <a name="other-common-issues"></a>Altri problemi comuni

- La delega non funziona se viene superata la soglia di 25 delegati e di 25 partecipanti.
    
- Il client di base di Skype for business non è supportato.
    
    > [!NOTE]
    > Se si installa il client di Skype for Business Basic, verrà rimosso e interrotta la delega. 
  
- Se il valore di **stato MAPI** non è **OK**, verificare che i valori **SIP** e **SMTP** corrispondano.
    
    > [!NOTE]
    > Dopo aver avviato Skype for business e Outlook, è possibile che lo stato MAPI venga visualizzato in diversi minuti come **OK** .
  
- La creazione di un gruppo di sicurezza e l'aggiunta delle autorizzazioni di delega per il gruppo di sicurezza non sono supportate.
    
- MAPI non è disponibile. Vedere [errore "MAPI non disponibile" nel client di Skype for Business 2016](https://support.microsoft.com/help/3147130).
    
- La cassetta postale di Exchange Online non è accessibile tramite il client Skype for business. In questo caso, Esegui il [test di connettività di Outlook](https://testconnectivity.microsoft.com/) per verificare che venga superato.
    
## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
