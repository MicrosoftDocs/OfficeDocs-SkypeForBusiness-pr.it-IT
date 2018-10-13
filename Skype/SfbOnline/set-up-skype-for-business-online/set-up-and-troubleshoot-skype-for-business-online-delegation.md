---
title: Configurare le deleghe e risolvere i problemi relativi alle deleghe in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: In questo articolo viene illustrato come impostare e risolvere i problemi Skype per la delega Business Online. In questo articolo vengono fornite indicazioni per suggerimenti per il programma di installazione, procedure consigliate e istruzioni sulla risoluzione dei problemi.
ms.openlocfilehash: e3131b28be1ad01e0965b2739dc152a627826d5e
ms.sourcegitcommit: 28e0e8043f418505039cd12407c927f454c141f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "25546676"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurare le deleghe e risolvere i problemi relativi alle deleghe in Skype for Business online

In questo articolo viene illustrato come impostare e risolvere i problemi Skype per la delega Business Online. In questo articolo vengono fornite indicazioni per suggerimenti per il programma di installazione, procedure consigliate e istruzioni sulla risoluzione dei problemi.
  
## <a name="guidelines-and-requirements"></a>Requisiti e le linee guida

### <a name="guidelines-for-delegation"></a>Linee guida per la delega

Configurazione e il recupero di delega per il corretto funzionamento dipende è seguendo le indicazioni seguenti:
  
- È necessario utilizzare Skype per 2015 Business completo client con gli aggiornamenti più recenti o le Skype per client completo 2016 Business.
    
- È necessario utilizzare il client di Outlook 2013 con gli aggiornamenti più recenti o del client Outlook 2016.
    
- Verificare che il delegante e computer di delegato di un profilo di posta elettronica di Outlook che è il server principale o il profilo predefinito. Un profilo di posta elettronica sia presente un solo account.
    
- Skype per le aziende per il delegante e il delegato deve essere utenti in linea. Inoltre, le cassette postali Exchange Server per ogni account deve essere entrambi Online o locale possono essere entrambi.
    
- Delegator sia il delegato devono utilizzare la stessa versione principale di Outlook.
    
- Il valore dell'attributo **EnableExchangeDelegateSync** deve impostare su **true** nel criterio del client. È possibile verificare questa impostazione eseguendo il cmdlet **Get-CSClientPolicy** in Skype di funzionalità di Business Online PowerShell.
    
- Delegator sia il delegato devono eseguire l'accesso a Skype per le aziende e Outlook contemporaneamente nella workstation diverse.
    
- Cassette postali condivise non sono supportate per Skype per la delega Business Online. Ciò avviene perché l'elenco di controllo di accesso (ACL) **sendonbehalf** non dispone di cassetta postale condivisa.
    
### <a name="skype-for-business-client-version-support"></a>Skype per il supporto di versione client Business

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype per Client di base di Business**| Non supportato |Non supportato
|**Skype per Business 2015**|È supportata| È supportata|
|**Skype per Business 2016**|È supportata| È supportata|

   
### <a name="licensing-requirements"></a>Requisiti di licenza

**Scenario di gestione delle licenze aziendale E3**

|**Licenza**|**Client**|**Note**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype per 2015 Business) utilizzato con 2016 Outlook o Outlook 2013  <br/> Skype per 2016 Business utilizzate con 2016 Outlook o Outlook 2013  <br/> |Skype per client Business Basic non supporta la delega.  <br/> Per i client Mac, è possibile delegare le chiamate ma non in riunioni.  <br/> |
|Aziendale E3 con sistema telefonico in Office 365 + Office 365 xCalling piano  <br/> |Lync 2013 (Skype per 2015 Business) utilizzato con 2016 Outlook o Outlook 2013  <br/> Skype per 2016 Business utilizzate con 2016 Outlook o Outlook 2013  <br/> Lync per Mac 2011  <br/> |Skype per client Business Basic non supporta la delega.  <br/> Per i client Mac, è possibile delegare le chiamate ma non in riunioni.  <br/> |
   
**Scenario di licenza Enterprise E5**

|**Licenza**|**Client**|**Note**|
|:-----|:-----|:-----|
|E5 Enterprise  <br/> |Lync 2013 (Skype per 2015 Business) utilizzato con 2016 Outlook o Outlook 2013.  <br/> Skype per 2016 Business utilizzate con 2016 Outlook o Outlook 2013  <br/> |Skype per client Business Basic non supporta la delega.  <br/> Per i client Mac, è possibile delegare le chiamate ma non in riunioni.  <br/> |
|Enterprise E5 e piano di chiamata di Office 365  <br/> |Skype per le aziende per Mac 2016  <br/> Lync 2013 (Skype per 2015 Business) utilizzato con 2016 Outlook o Outlook 2013  <br/> Skype per 2016 Business utilizzate con 2016 Outlook o Outlook 2013  <br/> Lync per Mac 2011  <br/> |Skype per client Business Basic non supporta la delega.  <br/> Per i client Mac, è possibile delegare le chiamate ma non in riunioni.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Impostare e verificare la delega

Per configurare Skype per la delega Business Online, procedere come segue:
  
### <a name="for-windows-clients"></a>Per i client Windows

 **Scheda inoltro di chiamata.**
  
1. Selezionare **Strumenti** > **Opzioni** > **le impostazioni di inoltro di chiamata**.
    
2. Selezionare **Modifica i membri delegati personali**.
    
3. Selezionare **Aggiungi**, selezionare il delegato che si desidera aggiungere e quindi scegliere **OK**.
    
 **Nessuna scheda inoltro di chiamata**
  
1. In Outlook, selezionare **File** > **Le impostazioni degli Account** > **Accesso delegato** > **Add**.
    
2. Individuare e quindi aggiungere il nome della persona che verrà il delegato.
    
3. Selezionare il menu **calendario** e quindi selezionare **Editor (lettura, creare e modificare elementi)**.
    
### <a name="for-mac-clients---lync"></a>Per i client Mac - Lync

 **Scheda inoltro di chiamata.**
  
- Se il client non dispone di una scheda **Inoltro di chiamata** con collegamento **Modifica i membri delegati personali** e delegante si trova in un computer Mac, delegante deve effettuare l'accesso a un computer basato su Windows per impostare la delega. Ciò avviene perché i client Mac non possono effettuare connessioni MAPI e questo è un requisito per stabilire Skype per la delega Business da Outlook.
    
### <a name="verify-success"></a>Verificare l'esito positivo

Se l'installazione viene eseguita correttamente, il delegato verrà visualizzato l'oggetto **è stato aggiunto come delegato per < nome >** messaggio e che viene creato il gruppo **persone per utente gestisce le chiamate** . Delegante dovrebbero essere visualizzati che viene creato il gruppo **delegati** .
  
> [!NOTE]
> Autorizzazioni di delega in genere vengono visualizzati all'interno di 30 minuti di processo di installazione. Tuttavia, il processo può richiedere fino a 24 ore. 
  
## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="common-issues"></a>Problemi comuni

- > **Problema 1** La voce del delegato viene ancora visualizzato nel gruppo di **persone per utente gestisce le chiamate** dopo che il delegante è rimosso il delegato dal client di Outlook.
    
  - > **Soluzione 1** In Skype per client di Business, destro il delegato nel gruppo **delegati** e quindi scegliere **Rimuovi dal gruppo**.
    
- > **Problema 2** Dopo che un client Outlook viene concesso l'accesso delegato, il messaggio di conferma e il gruppo **persone per utente gestisce le chiamate** non vengono visualizzati per il delegato.
    
  - > **Soluzione 2** Rimuovere la delega dal client Outlook, attendere 15 minuti per la replica e quindi aggiungere di nuovo il delegato.
    
### <a name="other-common-issues"></a>Altri problemi comuni

- Delega non funziona se supera la soglia di 25 delegante e 25 delegati.
    
- Skype per client Business Basic non è supportato.
    
    > [!NOTE]
    > Se si installa Skype per client di base di Business, rimuoverà e interrompere la delega. 
  
- Se il valore di **Stato MAPI** non **OK**, verificare che i valori **SIP** e **SMTP** corrispondano.
    
    > [!NOTE]
    > È possibile richiedere alcuni minuti per lo stato MAPI visualizzare come **OK** dopo aver avviato prima Skype per le aziende e Outlook.
  
- Creare un gruppo di sicurezza e aggiungere le autorizzazioni di delega per tale gruppo di sicurezza non è supportato.
    
- MAPI non è disponibile. Vedere [l'errore "MAPI non disponibile" in Skype per client 2016 Business](https://support.microsoft.com/en-us/help/3147130).
    
- La cassetta postale di Exchange Online non è accessibile tramite Skype per client di Business. In tal caso, eseguire il [test di connettività Outlook](https://testconnectivity.microsoft.com/) per assicurarsi che viene passato.
    
## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
