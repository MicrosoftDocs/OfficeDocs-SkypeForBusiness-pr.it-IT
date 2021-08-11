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
description: Questo articolo spiega come configurare e risolvere i problemi Skype for Business delega online. Questo articolo fornisce indicazioni per i suggerimenti per la configurazione, le procedure consigliate e i passaggi per la risoluzione dei problemi.
ms.openlocfilehash: c672006e8b78e5b3fb881da97e2ab3bbe65e465aa5981cc95fb2caf9bed39e4f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310175"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurare le deleghe e risolvere i problemi relativi alle deleghe in Skype for Business online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Questo articolo spiega come configurare e risolvere i problemi Skype for Business delega online. Questo articolo fornisce indicazioni per i suggerimenti per la configurazione, le procedure consigliate e i passaggi per la risoluzione dei problemi.
  
## <a name="guidelines-and-requirements"></a>Linee guida e requisiti

### <a name="guidelines-for-delegation"></a>Linee guida per la delega

La configurazione e il corretto funzionamento della delega dipendono dall'utente che segue queste linee guida:
  
- È necessario usare il client Skype for Business 2015 completo con gli aggiornamenti più recenti o il client completo Skype for Business 2016.
    
- È necessario usare il client Outlook 2013 con gli aggiornamenti più recenti o il client Outlook 2016 2013.
    
- Assicurarsi che il delegante e il computer delegato Outlook un profilo di posta elettronica principale o predefinito. Il profilo di posta elettronica deve contenere un solo account.
    
- Skype for Business per il delegante e il delegato devono essere utenti online. Inoltre, le Exchange Server per ogni account devono essere entrambe online o entrambe in locale.
    
- Sia il delegato che il delegato devono usare la stessa versione principale di Outlook.
    
- Il **valore dell'attributo EnableExchangeDelegateSync** deve essere impostato su **true** nei criteri client. È possibile verificare questa impostazione eseguendo il cmdlet **Get-CSClientPolicy** nel modulo di PowerShell Skype for Business Online.
    
- Sia il delegato che il delegato devono essere connessi a Skype for Business e Outlook contemporaneamente su workstation diverse.
    
- Le cassette postali condivise non sono supportate per Skype for Business delega online. Questo perché la cassetta postale condivisa non ha l'elenco di controllo di accesso (ACL) **sendonbehalf.**
    
### <a name="skype-for-business-client-version-support"></a>Skype for Business versione client

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Client di base di Lync/Skype for Business**| Non supportato |Non supportato
|**Skype for Business 2015**|Supportato| Supportato|
|**Skype for Business 2016**|Supportato| Supportato|

   
### <a name="licensing-requirements"></a>Requisiti di licenza

**Enterprise Scenario di gestione delle licenze di E3**

|**Licenza**|**Client**|**Note**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype for Business 2015) usato con Outlook 2013 o Outlook 2016  <br/> Skype for Business 2016 usato con Outlook 2013 o Outlook 2016  <br/> |Skype for Business Il client di base non supporta la delega.  <br/> Per i client Mac, è possibile delegare le chiamate ma non le riunioni.  <br/> |
|Enterprise E3 con Sistema telefonico di Office 365 + Office 365 xCalling Plan  <br/> |Lync 2013 (Skype for Business 2015) usato con Outlook 2013 o Outlook 2016  <br/> Skype for Business 2016 usato con Outlook 2013 o Outlook 2016  <br/> Lync per Mac 2011  <br/> |Skype for Business Il client di base non supporta la delega.  <br/> Per i client Mac, è possibile delegare le chiamate ma non le riunioni.  <br/> |
   
**Enterprise Scenario di licenza E5**

|**Licenza**|**Client**|**Note**|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |Lync 2013 (Skype for Business 2015) usato con Outlook 2013 o Outlook 2016.  <br/> Skype for Business 2016 usato con Outlook 2013 o Outlook 2016  <br/> |Skype for Business Il client di base non supporta la delega.  <br/> Per i client Mac, è possibile delegare le chiamate ma non le riunioni.  <br/> |
|Enterprise E5 plus Office 365 Calling Plan  <br/> |Skype for Business per Mac 2016  <br/> Lync 2013 (Skype for Business 2015) usato con Outlook 2013 o Outlook 2016  <br/> Skype for Business 2016 usato con Outlook 2013 o Outlook 2016  <br/> Lync per Mac 2011  <br/> |Skype for Business Il client di base non supporta la delega.  <br/> Per i client Mac, è possibile delegare le chiamate ma non le riunioni.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Configurare e verificare la delega

Per configurare la delega Skype for Business Online, seguire questa procedura:
  
### <a name="for-windows-clients"></a>Per Windows client

 **Scheda Inoltro di chiamata**
  
1. Selezionare **Strumenti**  >  **Opzioni Inoltro** di chiamata  >  **Impostazioni**.
    
2. Selezionare **Modifica membri delegati.**
    
3. Selezionare **Aggiungi**, selezionare il delegato da aggiungere e quindi scegliere **OK**.
    
 **Scheda Inoltro di chiamata non disponibile**
  
1. In Outlook selezionare **Account file** Impostazioni  >    >  **Delega accesso**  >  **aggiungi**.
    
2. Individuare e aggiungere il nome della persona che sarà il delegato.
    
3. Selezionare **il** menu Calendario e quindi scegliere Editor (è possibile **leggere, creare e modificare elementi)**.
    
### <a name="for-mac-clients---lync"></a>Per i client Mac - Lync

 **Scheda Inoltro di chiamata**
  
- Se il client non  ha una scheda Inoltro  di chiamata con il collegamento Modifica membri delegati e il delegante si trova in un computer Mac, il delegante deve accedere a un computer basato su Windows per configurare la delega. Questo è dovuto al fatto che i client Mac non possono effettuare connessioni MAPI e questo è un requisito per stabilire Skype for Business delega da Outlook.
    
### <a name="verify-success"></a>Verifica dell'esito positivo

Se la configurazione ha esito positivo, il delegato dovrebbe visualizzare il messaggio Si è stati aggiunti  come delegato per il messaggio>Nome < e anche che viene creato il gruppo Persone per cui si gestiscono le chiamate.  Il delegante dovrebbe vedere che il **gruppo Delegati** è stato creato.
  
> [!NOTE]
> Le autorizzazioni di delega vengono in genere visualizzate entro 30 minuti dal processo di configurazione. Tuttavia, il completamento di questo processo può richiedere fino a 24 ore. 
  
## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="common-issues"></a>Problemi comuni

- > **Problema 1** La voce delegata continua  a essere visualizzata nel gruppo Persone per cui si gestiscono le chiamate dopo che il delegante ha rimosso il delegato dal client Outlook delegato.
    
  - > **Risoluzione 1** Nel client Skype for Business fare clic con il pulsante destro del mouse sul delegato nel gruppo **Delegati** e quindi **scegliere Rimuovi dal gruppo**.
    
- > **Problema 2** Dopo che l'accesso delegato viene concesso tramite il client  Outlook, per il delegato non vengono visualizzati né il messaggio di conferma né il gruppo Persone per cui si gestiscono le chiamate.
    
  - > **Risoluzione 2** Rimuovere la delega dal client Outlook, attendere circa 15 minuti per la replica e quindi aggiungere di nuovo il delegato.
    
### <a name="other-common-issues"></a>Altri problemi comuni

- La delega non funziona se viene superata la soglia di 25 deleganti e 25 delegati.
    
- Il Skype for Business client Basic non è supportato.
    
    > [!NOTE]
    > Se si installa il client Skype for Business Basic, rimuoverà e interromperà la delega. 
  
- Se il **valore stato MAPI** non è **OK,** verificare che i valori **SIP** e **SMTP** corrispondano.
    
    > [!NOTE]
    > La visualizzazione dello stato MAPI come **OK** può richiedere alcuni minuti dopo l'avvio Skype for Business e Outlook.
  
- La creazione di un gruppo di sicurezza e l'aggiunta di autorizzazioni di delega per il gruppo di sicurezza non sono supportate.
    
- MAPI non è disponibile. Vedere [l'errore "MAPI non disponibile" nel client Skype for Business 2016.](https://support.microsoft.com/help/3147130)
    
- La Exchange Online non è accessibile tramite il client Skype for Business. In questo caso, eseguire il [test Outlook connettività](https://testconnectivity.microsoft.com/) per assicurarsi che passi.
    
## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
