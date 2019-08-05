---
title: Installare e aprire gli strumenti di amministrazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Questo argomento descrive come installare e aprire gli strumenti di amministrazione necessari per la distribuzione e la gestione di Skype for business.
ms.openlocfilehash: 612ea46fe8870944fa4b460b034bb9a7386a88bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186785"
---
# <a name="install-and-open-administrative-tools"></a>Installare e aprire gli strumenti di amministrazione

Questo argomento descrive come installare gli strumenti di amministrazione necessari per la distribuzione e la gestione di Skype for Business Server. Gli strumenti di amministrazione vengono installati per impostazione predefinita in ogni server che esegue Skype for Business Server. È inoltre possibile installare gli strumenti di amministrazione in altri computer, ad esempio le console amministrative dedicate. Ti consigliamo vivamente di installare gli strumenti di amministrazione in un computer che si trova nello stesso dominio o foresta della distribuzione di Skype for Business Server che stai creando, per assicurarti che la procedura di preparazione dei servizi di dominio Active Directory sia già completata. che consente di usare gli strumenti di amministrazione nel computer in un secondo momento per pubblicare la topologia. Assicurati anche di esaminare i requisiti necessari prima di installare o usare gli strumenti di amministrazione di Skype for Business Server. Vedere la documentazione relativa ai requisiti in [Skype for Business server 2019](../../SfBServer2019/plan/system-requirements.md) o [Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Se l'organizzazione richiede l'individuazione di Internet Information Services (IIS) e di tutti i servizi Web in un'unità diversa da un'unità di sistema, è possibile modificare il percorso della posizione di installazione per i file di Skype for Business Server nella finestra di dialogo Imposta. Se si installano i file di configurazione in questo percorso, incluso OCSCore. msi, anche il resto dei file di Skype for Business Server verrà distribuito nell'unità. 

## <a name="to-install-the-administrative-tools"></a>Per installare gli strumenti di amministrazione

1. Accedere come amministratore locale (requisito minimo) al computer in cui si vogliono installare gli strumenti di amministrazione. Se è stato eseguito l'accesso come utente standard in Windows e il controllo dell'account utente è abilitato, verrà richiesto l'amministratore locale o un nome utente e una password equivalenti al dominio.
2. Individuare il supporto di installazione nel computer e quindi fare doppio clic su \Setup\amd64\Setup.exe.
3. Se viene richiesto di installare Microsoft Visual C++ distribuibili, fare clic su **Sì**.
4. Nella pagina posizione di installazione fare clic su **OK**. Cambiare il percorso in un'altra posizione o in un'altra unità se è necessario installare i file in un'altra posizione.

    > [!Important]
    > Se l'organizzazione richiede l'individuazione di Internet Information Services (IIS) e di tutti i servizi Web in un'unità diversa da un'unità di sistema, è possibile modificare il percorso della posizione di installazione per i file di Skype for Business Server nella finestra di dialogo Imposta. Se si installano i file di configurazione in questo percorso, incluso OCSCore. msi, anche il resto dei file di Skype for Business Server verrà distribuito nell'unità. 

5. Nella pagina Contratto di licenza con l'utente finale verificare le condizioni di licenza, fare clic su **Accetto**e quindi fare clic su **OK**. Questo passaggio è obbligatorio prima di poter continuare.
6. Nella pagina distribuzione guidata fare clic su **installa strumenti amministratore**. 
7. Dopo aver completato l'installazione, fare clic su **Esci**.

Usare le procedure seguenti per aprire gli strumenti di amministrazione per distribuire, configurare o risolvere i problemi della topologia di Skype for Business Server.

- [Distribuzione guidata](#deployment-wizard)
- [Generatore di topologie](#topology-builder) 
- [Pannello di controllo di Skype for Business Server](#skype-for-business-server-control-panel)
- [Skype for Business Server Management Shell](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Distribuzione guidata

Usare la procedura seguente per avviare la distribuzione guidata localmente per aggiungere o rimuovere file di componenti.

**Per avviare la distribuzione guidata di Skype for Business Server**

1. Accedere al computer in cui è installata la distribuzione guidata di Skype for Business Server come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.
2. Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server**e quindi fare clic su **Skype for Business Server Deployment Wizard**.


## <a name="topology-builder"></a>Generatore di topologie 

Usare la procedura seguente per aprire il generatore di topologia per definire i server che si desidera distribuire nella topologia di Skype for Business Server.

**Per aprire il generatore di topologia di Skype for Business Server per progettare la topologia**

1. Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.
    > [!NOTE]
    > Puoi definire una topologia usando un account che è un membro del gruppo utenti locali, ma per leggere, pubblicare o abilitare una topologia, necessaria per installare Skype for Business Server in un server, devi usare un account membro del gruppo Domain Admins e TH e RTCUniversalServerAdmins Group, con autorizzazioni di controllo completo (ovvero, lettura, scrittura e modifica) nella condivisione file che si vuole usare per l'archiviazione di file in modo che il generatore di topologia possa configurare l'elenco di controllo di accesso discrezionale richiesto ( DACL) o un account con diritti utente equivalenti.
 
2. Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Skype for Business Server**e quindi fare clic su **Generatore di topologia di Skype for Business Server**.

## <a name="skype-for-business-server-control-panel"></a>Pannello di controllo di Skype for Business Server 

Usare una delle procedure seguenti per aprire il pannello di controllo di Skype for Business Server per gestire la configurazione di server, utenti, client e dispositivi nell'ambiente.

> [!NOTE]
> Puoi usare un account utente assegnato al ruolo CsAdministrator per eseguire tutte le attività nel pannello di controllo di Skype for Business Server. È possibile usare altri ruoli per accedere al pannello di controllo di Skype for Business Server per eseguire specifiche attività di amministrazione, in base all'attività che occorre eseguire. Ad esempio, puoi usare CSArchivingAdministrator per amministrare l'archiviazione nel pannello di controllo di Skype for Business Server. Per informazioni dettagliate sui ruoli, vedere [pianificazione per il controllo dell'accesso basato](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx)sui ruoli. Per informazioni dettagliate sui ruoli che è possibile usare per eseguire un'attività specifica, vedere la documentazione relativa all'attività. 

**Per aprire il pannello di controllo di Skype for Business Server da qualsiasi computer all'interno del firewall dell'organizzazione**

1. Da un account utente assegnato al ruolo CsAdministrator o da un altro ruolo che disponga dei diritti utente appropriati e delle autorizzazioni per l'attività da eseguire, accedere a qualsiasi computer della distribuzione interna con una risoluzione minima dello schermo di 1024 x 768.

    > [!IMPORTANT]
    > Se è stato configurato un semplice URL (Uniform Resource Locator) di amministrazione, è possibile accedere al pannello di controllo di Skype for Business Server da un browser Internet in uso in qualsiasi computer all'interno del firewall dell'organizzazione. Per informazioni dettagliate sulla configurazione dell'URL semplice di amministrazione, vedere [pianificazione di URL semplici](https://technet.microsoft.com/en-us/library/gg398287(v=ocs.15).aspx) e [modifica o configurazione di URL semplici](https://technet.microsoft.com/en-us/library/gg398063(v=ocs.15).aspx). 

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore configurato per l'organizzazione.

**Per aprire il pannello di controllo di Skype for Business Server in un computer con Skype for Business Server**

1. Da un account utente che fa parte del ruolo CsAdministrator o di un altro ruolo che disponga dei diritti utente e delle autorizzazioni appropriate per l'attività, accedere a un computer in cui è installato Skype for Business Server o, almeno , gli strumenti di amministrazione di Skype for Business Server. Per configurare le impostazioni, il computer deve avere una risoluzione minima dello schermo di 1024 x 768.
2. Avviare il pannello di controllo di Skype for Business Server: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**, scegliere **Skype for Business Server**e quindi fare clic su **Pannello di controllo di Skype for Business Server**.

## <a name="skype-for-business-server-management-shell"></a>Skype for Business Server Management Shell 

Usare la procedura seguente per aprire Skype for Business Server Management Shell per amministrare server, utenti, client e dispositivi nell'ambiente tramite la riga di comando.

> [!NOTE]
> Puoi usare un account utente assegnato al ruolo CsAdministrator per eseguire qualsiasi attività in Skype for Business Server Management Shell. È possibile accedere con altri ruoli per eseguire attività di amministrazione specifiche, a seconda dell'attività che occorre eseguire. Ad esempio, puoi usare CSArchivingAdministrator per eseguire i cmdlet correlati all'amministrazione dell'archiviazione. Per informazioni dettagliate sui ruoli, vedere [pianificazione per il controllo dell'accesso basato](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx)sui ruoli. Per informazioni dettagliate sui ruoli che è possibile usare per eseguire un cmdlet specifico, vedere la documentazione relativa al cmdlet.<br/><br/>Puoi anche eseguire determinati cmdlet usando un account utente nei gruppi RTCUniversalServerAdmins, RTCUniversalUserAdmins o RTCUniversalReadOnlyAdmins, a seconda del cmdlet. 

**Per aprire Skype for Business Server Management Shell**

Se si apre una finestra di Windows PowerShell invece di Skype for Business Server Management Shell, per impostazione predefinita non è possibile eseguire i cmdlet di Skype for Business Server. Per eseguire i cmdlet di Skype for Business Server dall'interno di Windows PowerShell, digitare quanto segue al prompt dei comandi di Windows PowerShell:

`Import-Module Lync`

Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business**server e quindi fare clic su **Skype for Business Server Management Shell**.
