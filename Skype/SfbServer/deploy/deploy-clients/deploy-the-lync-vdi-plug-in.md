---
title: Distribuire il plug-in VDI di Lync con Skype for Business Server
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: In questo argomento vengono illustrate le procedure di distribuzione per l'utilizzo di Skype for business durante la connessione a un desktop virtuale remoto.
ms.openlocfilehash: f7ff99045c861c4435675d9e9e86deaedd499c10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805936"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Distribuire il plug-in VDI di Lync con Skype for Business Server
 
In questo argomento vengono illustrate le procedure di distribuzione per l'utilizzo di Skype for business durante la connessione a un desktop virtuale remoto. Le considerazioni relative alla pianificazione sono disponibili [in Plan for Skype for business in VDI Environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).
  
Un ambiente VDI (Virtual Desktop Infrastructure) viene utilizzato in alcune organizzazioni in cui i problemi di sicurezza e conformità sono particolarmente sensibili. Gli utenti si trovano nei computer Windows locali e utilizzano client su un desktop virtuale. L'utilizzo di Skype for business su una connessione di questo tipo richiede un ulteriore software plug-in VDI.
  
Sono disponibili due soluzioni per il componente plug-in VDI-uno offerto da Microsoft e uno offerto da Citrix. Microsoft consiglia di utilizzare la nuova soluzione per il pacchetto di ottimizzazione in tempo reale HDX in nuove distribuzioni, ma continuerà a supportare il plug-in VDI originale di Lync per il resto del ciclo di vita. 
  
In questo argomento vengono fornite informazioni dettagliate sulla distribuzione del plug-in Microsoft Lync VDI, che è supportato solo in Windows 7 e Windows 8 o Windows Server 2008 e supporta solo i client Lync 2013 o Skype for business. Non vi sono piani per l'aggiornamento di questo plugin, ma il [pacchetto di ottimizzazione in tempo reale di Citrix HDX](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) per Skype for business verrà aggiornato in base alle esigenze.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Preparare l'ambiente per il plug-in VDI di Lync
<a name="Prepare_vdi"> </a>

1. In Skype for Business Server, assicurarsi che EnableMediaRedirection sia impostato su TRUE per tutti gli utenti di plug-in di Lync VDI. Per informazioni dettagliate, vedere gli argomenti della Guida per il cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) e il cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .
    
2. Nel server Data Center, installare il client Skype for business su tutti i desktop virtuali.
    
3. Nei computer locali installare il plug-in VDI di Lync.
    
    Gli utenti dovrebbero ora connettere un dispositivo come un auricolare o una webcam al computer locale.
    
## <a name="configure-remote-desktop-connection-settings"></a>Configurare le impostazioni di connessione Desktop remoto
<a name="Prepare_vdi"> </a>

Per preparare la connessione Desktop remoto per il plug-in VDI di Lync, eseguire la procedura seguente nel computer locale:
  
1. Se il computer locale esegue Windows 8, ignorare questo passaggio. Se il computer locale esegue Windows 7 con SP1, installare la versione più recente di Windows 8 del [client Servizi Desktop remoto](https://go.microsoft.com/fwlink/p/?LinkId=268032).
    
2. Avviare il client Servizi Desktop remoto facendo clic sul pulsante **Start** e quindi su **Connessione desktop remoto**.
    
3. Fare clic su **Opzioni**.
    
4. Fare clic sulla scheda **risorse locali** . In **audio remoto** fare clic su **Impostazioni** e quindi eseguire le operazioni seguenti:
    
   - In **riproduzione audio remota** selezionare **Riproduci su questo computer**.
    
   - In **registrazione audio remota** selezionare **non registrare**.
    
   - Fare clic su **OK**.
    
5. Fare clic sulla scheda **Experience** . In **prestazioni**, deselezionare la casella di controllo relativa alla **memorizzazione nella cache della bitmap persistente** .
    
6. Fare clic sulla scheda **generale** . In **computer**, digitare il nome del desktop virtuale e quindi fare clic su **Connetti**. 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>Accedere e usare Skype for business sul desktop virtuale
<a name="SfB_signin"> </a>

Dopo aver abilitato il plug-in VDI di Lync, l'utente segue questa procedura quando si accede a Skype for business sul desktop virtuale.
  
1. L'utente digita le proprie credenziali nel client Skype for business in esecuzione sul desktop virtuale.
    
2. Dopo che Skype for business ha rilevato il plug-in VDI di Lync, Skype for business richiede all'utente di immettere di nuovo le credenziali. In questa finestra di dialogo è consigliabile che l'utente selezioni la casella di controllo **Salva la password** in modo che non venga richiesta di nuovo l'immissione delle credenziali per gli accessi successivi.
    
3. Skype for business inizia l'accoppiamento con il plug-in VDI di Lync. In questo caso, il client visualizza due icone nella barra di stato di Skype for business. L'icona in basso a sinistra indica che non sono disponibili dispositivi audio e l'icona lampeggiante in basso a destra indica che l'accoppiamento VDI è in corso: a. Dopo che l'accoppiamento VDI ha esito positivo, le icone cambiano per indicare il dispositivo audio che verrà utilizzato per le chiamate e il successo dell'accoppiamento VDI: b. L'utente può ora vedere la propria presenza sui dispositivi compatibili con Skype for business che sono connessi al computer locale e rispondere alle chiamate come al solito.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Risoluzione dei problemi relativi al plug-in VDI di Lync
<a name="tshoot_VDI"> </a>

Se si verificano problemi dopo l'installazione del plug-in VDI di Lync, fare riferimento alle sezioni seguenti.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Problemi relativi all'installazione del plug-in VDI di Lync

Se si verificano problemi relativi all'installazione del plug-in VDI di Lync, vedere quanto segue:
  
- Verificare che nella cartella specificata vi sia sufficiente spazio per le variabili di sistema TEMP e TMP.
    
- Verificare che la protezione dalla scrittura sia disattivata. Per istruzioni, fare riferimento alla documentazione del produttore del dispositivo.
    
### <a name="troubleshooting-issues-with-pairing"></a>Risoluzione dei problemi di abbinamento

Quando l'accoppiamento di plug-in di Lync VDI ha esito negativo, l'icona di accoppiamento in basso a destra viene visualizzata come "X" rossa, come mostrato nell'esempio seguente: 
  
Di seguito sono riportate le possibili cause degli errori e le azioni che è possibile eseguire per risolvere il problema. 
  
- **Sono state inserite credenziali non corrette durante l'accesso.**
    
    L'utente deve disconnettersi da Skype for business e accedere di nuovo con le credenziali corrette. Verrà visualizzata di nuovo la finestra di dialogo di abbinamento che segnalerà se l'abbinamento è andato a buon fine.
    
- **È in esecuzione un'altra istanza del client desktop remoto.**
    
    Se si utilizza la connessione Desktop remoto in Windows, gli utenti devono eseguire le operazioni seguenti:
    
1. Avviare Gestione attività: premere **Alt+Ctrl+Canc** e quindi fare clic su **Avvia Gestione attività**.
    
2. Fare clic sulla scheda **Processi** e cercare tutti i processi denominati **mstsc.exe** nell'elenco.
    
3. Selezionare ogni processo **mstsc.exe** e fare clic su **Termina processo**. 
    
4. Avviare una nuova sessione di desktop remoto e riprovare a connettersi. 
    
- **I file necessari non sono installati correttamente.**
    
    Dopo aver installato il plug-in nel computer locale, verificare che questi file siano presenti in C:\Programmi\Microsoft Office\Office15 (o nella lettera di unità appropriata):
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **Il client Skype for business è in esecuzione nel computer locale.**
    
    Per utilizzare il plug-in VDI di Lync, non è necessario che un client Skype for business sia in esecuzione nel computer locale, altrimenti l'accoppiamento avrà esito negativo. Come procedura consigliata, l'utente non deve installare un client Skype for business nel computer locale.
    
## <a name="see-also"></a>Vedere anche
<a name="tshoot_VDI"> </a>

[Pianificare Skype for business in ambienti VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
