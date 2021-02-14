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
description: Questo articolo spiega come configurare e risolvere i problemi relativi alla delega di Skype for Business online. Questo articolo fornisce indicazioni per la configurazione consigliata, procedure consigliate e procedure di risoluzione dei problemi.
ms.openlocfilehash: 6774fe36760e6a9c53808f33f7a842d5460e0f4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010799"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurare le deleghe e risolvere i problemi relativi alle deleghe in Skype for Business online

Questo articolo spiega come configurare e risolvere i problemi relativi alla delega di Skype for Business online. Questo articolo fornisce indicazioni per la configurazione consigliata, procedure consigliate e procedure di risoluzione dei problemi.
  
## <a name="guidelines-and-requirements"></a>Linee guida e requisiti

### <a name="guidelines-for-delegation"></a>Linee guida per la delega

La configurazione e il corretto funzionamento della delega dipendono dalle linee guida seguenti:
  
- È necessario utilizzare il client completo Skype for Business 2015 con gli aggiornamenti più recenti o il client completo di Skype for Business 2016.
    
- È necessario usare il client Outlook 2013 con gli aggiornamenti più recenti o con il client Outlook 2016.
    
- Assicurarsi che il delegante e i computer delegati dispongono di un profilo di posta di Outlook che sia quello primario o quello predefinito. Il profilo di posta elettronica deve contenere un solo account.
    
- Skype for Business per il delegante e il delegato devono essere utenti online. Inoltre, le Exchange Server per ogni account devono essere entrambe online o entrambe in locale.
    
- Sia il delegante che il delegato devono usare la stessa versione principale di Outlook.
    
- Il **valore dell'attributo EnableExchangeDelegateSync** deve essere impostato su **true** nei criteri client. Per verificare questa impostazione, eseguire il cmdlet **Get-CSClientPolicy** nel modulo PowerShell di Skype for Business Online.
    
- Sia il delegante che il delegato devono aver effettuato l'accesso a Skype for Business e Outlook contemporaneamente su workstation diverse.
    
- Le cassette postali condivise non sono supportate per la delega di Skype for Business Online. Ciò è dovuto al fatto che la cassetta postale condivisa non ha l'elenco di controllo di accesso (ACL) **sendonbehalf.**
    
### <a name="skype-for-business-client-version-support"></a>Supporto della versione del client Skype for Business

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype for Business Basic Client**| Non supportato |Non supportato
|**Skype for Business 2015**|Supportata| Supportata|
|**Skype for Business 2016**|Supportata| Supportata|

   
### <a name="licensing-requirements"></a>Requisiti di licenza

**Scenario di gestione delle licenze Enterprise E3**

|**Licenza**|**Client**|**Note**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype for Business 2015) usato con Outlook 2013 o Outlook 2016  <br/> Skype for Business 2016 utilizzato con Outlook 2013 o Outlook 2016  <br/> |Il client Skype for Business Basic non supporta la delega.  <br/> Per i client Mac, è possibile delegare le chiamate ma non le riunioni.  <br/> |
|Enterprise E3 con Sistema telefonico Office 365 + Office 365 xCalling Plan  <br/> |Lync 2013 (Skype for Business 2015) usato con Outlook 2013 o Outlook 2016  <br/> Skype for Business 2016 utilizzato con Outlook 2013 o Outlook 2016  <br/> Lync per Mac 2011  <br/> |Il client Skype for Business Basic non supporta la delega.  <br/> Per i client Mac, è possibile delegare le chiamate ma non le riunioni.  <br/> |
   
**Scenario di gestione delle licenze Enterprise E5**

|**Licenza**|**Client**|**Note**|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |Lync 2013 (Skype for Business 2015) usato con Outlook 2013 o Outlook 2016.  <br/> Skype for Business 2016 utilizzato con Outlook 2013 o Outlook 2016  <br/> |Il client Skype for Business Basic non supporta la delega.  <br/> Per i client Mac, è possibile delegare le chiamate ma non le riunioni.  <br/> |
|Enterprise E5 plus Office 365 Calling Plan  <br/> |Skype for Business per Mac 2016  <br/> Lync 2013 (Skype for Business 2015) usato con Outlook 2013 o Outlook 2016  <br/> Skype for Business 2016 utilizzato con Outlook 2013 o Outlook 2016  <br/> Lync per Mac 2011  <br/> |Il client Skype for Business Basic non supporta la delega.  <br/> Per i client Mac, è possibile delegare le chiamate ma non le riunioni.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Configurare e verificare la delega

Per configurare la delega di Skype for Business online, seguire questa procedura:
  
### <a name="for-windows-clients"></a>Per client Windows

 **Scheda Inoltro di chiamata**
  
1. Selezionare **Strumenti -**  >  **Impostazioni** inoltro di  >  **chiamata.**
    
2. Selezionare **Modifica i membri delegati.**
    
3. Selezionare **Aggiungi,** selezionare il delegato da aggiungere e quindi scegliere **OK.**
    
 **Scheda Inoltro di chiamata non disponibile**
  
1. In Outlook selezionare **Impostazioni account file**,  >  **Accesso** delegato  >  **-**  >  **Aggiungi.**
    
2. Individuare e aggiungere il nome della persona che sarà il delegato.
    
3. Selezionare il menu **Calendario** e quindi **Selezionare Editor (lettura, creazione e modifica di elementi).**
    
### <a name="for-mac-clients---lync"></a>Per client Mac - Lync

 **Scheda Inoltro di chiamata**
  
- Se il client non ha una scheda **Inoltro** di chiamata con il collegamento Modifica i membri delegati personale e il delegante si trova in un computer Mac, il delegante deve accedere a un computer basato su Windows per poter configurare la delega.  Questo perché i client Mac non possono effettuare connessioni MAPI e questo è un requisito per stabilire la delega di Skype for Business da Outlook.
    
### <a name="verify-success"></a>Verifica dell'esito positivo

Se la configurazione riesce, il delegato dovrebbe visualizzare il messaggio Che l'utente è stato aggiunto  come delegato per il>Nome del **<** e che è stato creato anche il gruppo Persone per cui si gestiscono le chiamate. Il delegante dovrebbe vedere che è **stato** creato il gruppo Delegati.
  
> [!NOTE]
> Le autorizzazioni di delega vengono in genere visualizzate entro 30 minuti dal processo di configurazione. Tuttavia, il completamento di questo processo può richiedere fino a 24 ore. 
  
## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="common-issues"></a>Problemi comuni

- > **Problema 1** L'immissione del delegato  continua a essere visualizzata nel gruppo Persone per cui si gestiscono le chiamate dopo che il delegante ha rimosso il delegato dal client Outlook.
    
  - > **Risoluzione 1** Nel client Skype for Business fare clic  con il pulsante destro del mouse sul delegato nel gruppo Delegati e quindi scegliere **Rimuovi dal gruppo.**
    
- > **Problema 2** Dopo aver concesso l'accesso come delegato tramite  il client Outlook, per il delegato non vengono visualizzati né il messaggio di conferma né il gruppo Persone per cui si gestiscono le chiamate.
    
  - > **Risoluzione 2** Rimuovere la delega dal client Outlook, attendere circa 15 minuti per la replica e quindi aggiungere di nuovo il delegato.
    
### <a name="other-common-issues"></a>Altri problemi comuni

- La delega non funziona se viene superata la soglia di 25 deleganti e 25 delegati.
    
- Il client Skype for Business Basic non è supportato.
    
    > [!NOTE]
    > Se installi il client Skype for Business Basic, questo rimuoverà e interromperà la delega. 
  
- Se il **valore di Stato MAPI** non è **OK,** verificare che i valori **SIP** e **SMTP** corrispondano.
    
    > [!NOTE]
    > Dopo l'avvio di Skype for Business  e Outlook, lo stato MAPI può richiedere alcuni minuti.
  
- La creazione di un gruppo di sicurezza e l'aggiunta di autorizzazioni di delega per tale gruppo di sicurezza non è supportata.
    
- MAPI non è disponibile. Vedere [l'errore "MAPI non disponibile" nel client Skype for Business 2016.](https://support.microsoft.com/help/3147130)
    
- La cassetta postale di Exchange Online non è accessibile tramite il client Skype for Business. In questo caso, eseguire il [test di connettività di Outlook](https://testconnectivity.microsoft.com/) per assicurarsi che passi.
    
## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
