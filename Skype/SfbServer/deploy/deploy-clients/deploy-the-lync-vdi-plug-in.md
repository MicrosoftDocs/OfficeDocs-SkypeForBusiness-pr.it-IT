---
title: Distribuire il plug-in di Lync VDI con Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: In questo argomento vengono illustrate le procedure di distribuzione per l'uso di Skype for business durante la connessione a un desktop virtuale remoto.
ms.openlocfilehash: 8892bf8b8772bdb301f914bca134d61e67ea934b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234404"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Distribuire il plug-in di Lync VDI con Skype for Business Server
 
In questo argomento vengono illustrate le procedure di distribuzione per l'uso di Skype for business durante la connessione a un desktop virtuale remoto. Le considerazioni sulla pianificazione sono disponibili [in piano per Skype for business in ambienti VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md).
  
In alcune organizzazioni viene usato un ambiente VDI (Virtual Desktop Infrastructure) in cui i problemi di sicurezza e conformità sono particolarmente sensibili. I loro utenti si trovano in computer Windows locali e usano i client su un desktop virtuale. L'uso di Skype for business su una connessione simile richiede un ulteriore software di plug-in VDI.
  
Sono disponibili due soluzioni per il componente plug-in VDI-uno offerto da Microsoft e uno offerto da Citrix. Microsoft consiglia di usare la nuova soluzione per l'ottimizzazione in tempo reale di HDX in nuove distribuzioni, ma continuerà a supportare il plug-in originale di Lync VDI per il resto del ciclo di vita. 
  
Questo argomento fornisce informazioni dettagliate sulla distribuzione del plug-in Microsoft Lync VDI, supportato solo in Windows 7 e Windows 8 o Windows Server 2008, e supporta solo i client Lync 2013 o Skype for business. Non ci sono piani per aggiornare questo plug-in, ma il [pacchetto di ottimizzazione in realtime di Citrix HDX](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) per Skype for business verrà aggiornato in base alle esigenze.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Preparare l'ambiente per il plug-in di Lync VDI
<a name="Prepare_vdi"> </a>

1. In Skype for Business Server verificare che EnableMediaRedirection sia impostato su TRUE per tutti gli utenti del plug-in di Lync VDI. Per informazioni dettagliate, vedere gli argomenti della Guida relativi al cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) e al cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .
    
2. Nel server Data Center installare il client Skype for business in tutti i desktop virtuali.
    
3. Nei computer locali installare il plug-in di Lync VDI.
    
    Gli utenti devono ora connettere un dispositivo come un auricolare o una webcam al computer locale.
    
## <a name="configure-remote-desktop-connection-settings"></a>Configurare le impostazioni di connessione Desktop remoto
<a name="Prepare_vdi"> </a>

Per preparare la connessione Desktop remoto per il plug-in di Lync VDI, seguire questa procedura nel computer locale:
  
1. Se il computer locale è in uso in Windows 8, ignorare questo passaggio. Se nel computer locale è in esecuzione Windows 7 con SP1, installare la versione più recente di Windows 8 del [client di Servizi Desktop remoto](https://go.microsoft.com/fwlink/p/?LinkId=268032).
    
2. Avviare il client Servizi Desktop remoto facendo clic su **Start**e quindi su **Connessione desktop remoto**.
    
3. Fare clic su **Opzioni**.
    
4. Fare clic sulla scheda **risorse locali** . In **audio remoto**fare clic su **Impostazioni**e quindi eseguire le operazioni seguenti:
    
   - In **riproduzione audio remota**selezionare Riproduci **in questo computer**.
    
   - In **registrazione audio remota**selezionare non **registrare**.
    
   - Fare clic su **OK**.
    
5. Fare clic sulla scheda **esperienza** . In **prestazioni**deselezionare la casella di controllo **memorizzazione nella cache persistente della bitmap** .
    
6. Fare clic sulla scheda **generale** . In **computer**Digitare il nome del desktop virtuale e quindi fare clic su **Connetti**. 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>Accedere e usare Skype for business sul desktop virtuale
<a name="SfB_signin"> </a>

Dopo aver abilitato il plug-in di Lync VDI, l'utente seguirà questi passaggi quando si accede a Skype for business sul desktop virtuale.
  
1. L'utente digita le proprie credenziali nel client Skype for business in uso sul desktop virtuale.
    
2. Dopo che Skype for business ha rilevato il plug-in di Lync VDI, Skype for business chiede all'utente di immettere di nuovo le credenziali. In questa finestra di dialogo è consigliabile selezionare la casella di controllo **Salva la password** in modo che non venga richiesto di immettere le credenziali durante l'accesso successivo.
    
3. Skype for business inizia l'associazione con il plug-in di Lync VDI. In questo caso, il client visualizza due icone nella barra di stato di Skype for business. L'icona nell'angolo in basso a sinistra indica che non sono disponibili dispositivi audio e l'icona lampeggiante in basso a destra indica che è in corso l'associazione VDI: a. Dopo aver completato l'associazione VDI, le icone cambiano per indicare il dispositivo audio che verrà usato per le chiamate e il successo dell'associazione VDI: b. L'utente può ora vedere la sua presenza nei dispositivi compatibili con Skype for business collegati al computer locale e rispondere alle chiamate come di consueto.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Risolvere i problemi relativi al plug-in di Lync VDI
<a name="tshoot_VDI"> </a>

Se si verificano problemi dopo l'installazione del plug-in di Lync VDI, vedere le sezioni seguenti.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Problemi con l'installazione del plug-in di Lync VDI

In caso di problemi con l'installazione del plug-in di Lync VDI, verificare quanto segue:
  
- Verificare che nella cartella specificata nelle variabili di sistema TEMP e TMP sia disponibile spazio sufficiente.
    
- Verificare che la protezione da scrittura sia disattivata. Per istruzioni, vedere la documentazione del produttore del dispositivo.
    
### <a name="troubleshooting-issues-with-pairing"></a>Risoluzione dei problemi di associazione

Quando l'associazione dei plug-in di Lync VDI non riesce, l'icona di associazione nell'angolo in basso a destra viene visualizzata come "X" rossa, come illustrato di seguito: 
  
Di seguito sono riportate le possibili cause degli errori e le azioni che è possibile eseguire per risolvere il problema. 
  
- **L'utente ha immesso credenziali non corrette durante l'accesso.**
    
    L'utente deve disconnettersi da Skype for business ed eseguire di nuovo l'accesso con le credenziali corrette. La finestra di dialogo Associazione verrà ricomparsa e mostrerà se l'associazione ha esito positivo.
    
- **È in corso un'altra istanza del client desktop remoto.**
    
    Se si usa la connessione Desktop remoto in Windows, gli utenti devono eseguire le operazioni seguenti:
    
1. Avviare Task Manager: premere **ALT + CTRL + CANC**e quindi fare clic su **Avvia Gestione attività**.
    
2. Fare clic sulla scheda **processi** e cercare tutti i processi denominati **mstsc. exe** nell'elenco.
    
3. Evidenziare ogni processo **mstsc. exe** e quindi fare clic su **Termina processo**. 
    
4. Avviare una nuova sessione di desktop remoto e riprovare a connettersi. 
    
- **I file necessari non sono stati installati correttamente.**
    
    Dopo avere installato il plug-in nel computer locale, verificare che questi file siano presenti in C:\Programmi\Microsoft Office\Office15 (o nella lettera di unità appropriata):
    
  - LyncVdiPlugin. dll
    
  - UcVdi. dll
    
- **Il client Skype for business è in uso nel computer locale.**
    
    Per usare il plug-in di Lync VDI, non è necessario che un client Skype for business sia in esecuzione nel computer locale, altrimenti l'associazione non riuscirà. Come procedura consigliata, l'utente non deve installare un client Skype for business nel computer locale.
    
## <a name="see-also"></a>Vedere anche
<a name="tshoot_VDI"> </a>

[Pianificare Skype for business in ambienti VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
