---
title: Distribuire il plug-in VDI di Lync con Skype for Business Server
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: In questo argomento vengono illustrate le procedure di distribuzione per l'Skype for Business durante la connessione a un desktop virtuale remoto.
ms.openlocfilehash: 853bcfcc41d058983c0aabb2868351f1f59de08e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840568"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Distribuire il plug-in VDI di Lync con Skype for Business Server
 
In questo argomento vengono illustrate le procedure di distribuzione per l'Skype for Business durante la connessione a un desktop virtuale remoto. Considerazioni sulla pianificazione sono [disponibili in Plan for Skype for Business in VDI environments.](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
  
Un Virtual Desktop Infrastructure (VDI) viene utilizzato in alcune organizzazioni in cui i problemi di sicurezza e conformità sono particolarmente sensibili. Gli utenti sono in computer Windows e utilizzano client su un desktop virtuale. L Skype for Business su una connessione come questa richiede software aggiuntivo per plug-in VDI.
  
Sono disponibili due soluzioni per il componente plug-in VDI, una offerta da Microsoft e una offerta da Citrix. Microsoft consiglia di utilizzare la nuova soluzione HDX RealTime Optimization Pack nelle nuove distribuzioni, ma continuerà a supportare il plug-in VDI di Lync originale per il resto del ciclo di vita. 
  
In questo argomento vengono fornite informazioni dettagliate sulla distribuzione del plug-in VDI di Microsoft Lync, supportato solo in Windows 7 e Windows 8 o Windows Server 2008 e supporta solo i client Lync 2013 o Skype for Business. Non ci sono piani per aggiornare questo plug-in, ma [citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) per Skype for Business verrà aggiornato in base alle esigenze.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Preparare l'ambiente per il plug-in VDI di Lync
<a name="Prepare_vdi"> </a>

1. In Skype for Business Server, verificare che EnableMediaRedirection sia impostato su TRUE per tutti gli utenti del plug-in VDI lync. Per informazioni dettagliate, vedere gli argomenti della Guida relativi al cmdlet [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps) e al cmdlet [Set-CsClientPolicy.](/powershell/module/skype/set-csclientpolicy?view=skype-ps)
    
2. Nel server del data center installare il client Skype for Business su tutti i desktop virtuali.
    
3. Nei computer locali installare il plug-in VDI di Lync.
    
    Gli utenti devono ora connettere un dispositivo, ad esempio una cuffia o una webcam, al computer locale.
    
## <a name="configure-remote-desktop-connection-settings"></a>Configurare le impostazioni di Connessione Desktop remoto
<a name="Prepare_vdi"> </a>

Per preparare Connessione Desktop remoto per il plug-in VDI lync, eseguire la procedura seguente nel computer locale:
  
1. Se il computer locale esegue Windows 8, ignorare questo passaggio. Se il computer locale esegue Windows 7 con SP1, installare la versione Windows 8 più recente del client Servizi [Desktop remoto.](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients)
    
2. Avviare il client Servizi Desktop remoto facendo clic **sul pulsante Start** e quindi su Connessione Desktop **remoto.**
    
3. Fare clic su **Opzioni**.
    
4. Fare clic **sulla scheda Risorse** locali. In **Audio remoto** fare clic **Impostazioni** e quindi eseguire le operazioni seguenti:
    
   - In **Riproduzione audio remota** selezionare **Riproduci nel computer.**
    
   - In **Registrazione audio remota** selezionare Non **registrare**.
    
   - Fare clic su **OK**.
    
5. Fare clic **sulla scheda** Esperienza. In **Prestazioni** deselezionare la **casella di controllo Cache bitmap** persistente.
    
6. Fare clic **sulla scheda** Generale. In **Computer** digitare il nome del desktop virtuale e quindi fare clic su **Connessione**. 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>Accedere e usare Skype for Business sul desktop virtuale
<a name="SfB_signin"> </a>

Dopo aver abilitato il plug-in VDI di Lync, l'utente segue questi passaggi quando accede a Skype for Business sul desktop virtuale.
  
1. L'utente specifica le proprie credenziali nel client Skype for Business in esecuzione sul desktop virtuale.
    
2. Dopo Skype for Business il plug-in VDI lync, Skype for Business all'utente di immettere di nuovo le credenziali. In questa finestra di dialogo è consigliabile che l'utente selezioni la casella di controllo **Salva la password** in modo che non venga richiesta di nuovo l'immissione delle credenziali per gli accessi successivi.
    
3. Skype for Business inizia l'associazione con il plug-in VDI di Lync. In questo caso, il client visualizza due icone nella barra Skype for Business stato. L'icona in basso a sinistra indica che non sono disponibili dispositivi audio e l'icona lampeggiante in basso a destra indica che è in corso l'associazione VDI: a. Una volta completata l'associazione VDI, le icone cambiano per indicare il dispositivo audio che verrà utilizzato per le chiamate e l'associazione VDI riuscita: b. L'utente può ora visualizzare la propria presenza Skype for Business dispositivi compatibili connessi al computer locale e effettuare e rispondere alle chiamate come di consueto.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Risolvere i problemi relativi al plug-in VDI di Lync
<a name="tshoot_VDI"> </a>

Fare riferimento alle sezioni seguenti se si verificano problemi dopo l'installazione del plug-in VDI di Lync.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Problemi con l'installazione del plug-in VDI di Lync

Se si verificano problemi con l'installazione del plug-in VDI di Lync, verificare quanto segue:
  
- Verificare che nella cartella specificata vi sia sufficiente spazio per le variabili di sistema TEMP e TMP.
    
- Verificare che la protezione dalla scrittura sia disattivata. Per istruzioni, fai riferimento alla documentazione del produttore del dispositivo.
    
### <a name="troubleshooting-issues-with-pairing"></a>Risoluzione dei problemi di abbinamento

Quando l'associazione del plug-in VDI di Lync non riesce, l'icona di associazione in basso a destra viene visualizzata come una "X" rossa, come illustrato: 
  
Di seguito sono riportati i possibili motivi degli errori e le azioni che è possibile eseguire per correggere il problema. 
  
- **Sono state inserite credenziali non corrette durante l'accesso.**
    
    L'utente deve disconnettersi Skype for Business e accedere di nuovo con le credenziali corrette. Verrà visualizzata di nuovo la finestra di dialogo di abbinamento che segnalerà se l'abbinamento è andato a buon fine.
    
- **È in esecuzione un'altra istanza del client desktop remoto.**
    
    Se usano Connessione Desktop remoto in Windows, gli utenti devono eseguire le operazioni seguenti:
    
1. Avviare Gestione attività: premere **Alt+Ctrl+Canc** e quindi fare clic su **Avvia Gestione attività**.
    
2. Fare clic sulla scheda **Processi** e cercare tutti i processi denominati **mstsc.exe** nell'elenco.
    
3. Selezionare ogni processo **mstsc.exe** e fare clic su **Termina processo**. 
    
4. Avviare una nuova sessione di desktop remoto e riprovare a connettersi. 
    
- **I file necessari non sono installati correttamente.**
    
    Dopo aver installato il plug-in nel computer locale, verificare che questi file siano presenti in C:\Programmi\Microsoft Office\Office15 (o nella lettera di unità appropriata):
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **Il Skype for Business client è in esecuzione nel computer locale.**
    
    Per utilizzare il plug-in VDI lync, un client Skype for Business non deve essere in esecuzione nel computer locale, altrimenti l'associazione avrà esito negativo. Come procedura consigliata, l'utente non deve installare un client Skype for Business nel computer locale.
    
## <a name="see-also"></a>Vedere anche
<a name="tshoot_VDI"> </a>

[Pianificare la Skype for Business in ambienti VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md)