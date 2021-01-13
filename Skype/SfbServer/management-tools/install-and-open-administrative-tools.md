---
title: Installare e aprire strumenti di amministrazione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In questo argomento viene descritto come installare e aprire gli strumenti di amministrazione necessari per la distribuzione e la gestione di Skype for business.
ms.openlocfilehash: d31fe784b62a5d709049dc5061e323034065df37
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835096"
---
# <a name="install-and-open-administrative-tools"></a>Installare e aprire strumenti di amministrazione

In questo argomento viene descritto come installare gli strumenti di amministrazione necessari per la distribuzione e la gestione di Skype for Business Server. Gli strumenti di amministrazione sono installati per impostazione predefinita in ogni server che esegue Skype for Business Server. Inoltre, è possibile installare gli strumenti di amministrazione in altri computer, ad esempio le console amministrative dedicate. È consigliabile installare gli strumenti di amministrazione in un computer che si trova nello stesso dominio o foresta della distribuzione di Skype for Business Server che si sta creando, per assicurarsi che i passaggi di preparazione di servizi di dominio Active Directory siano già stati completati, consentendo di utilizzare gli strumenti di amministrazione di quel computer in un secondo momento per pubblicare la topologia. Controllare anche i requisiti necessari prima di installare o utilizzare gli strumenti di amministrazione di Skype for Business Server. Vedere la documentazione relativa ai requisiti in [Skype for Business server 2019](../../SfBServer2019/plan/system-requirements.md) o [Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Se l'organizzazione richiede l'individuazione di Internet Information Services (IIS) e di tutti i servizi Web in un'unità diversa dall'unità di sistema, è possibile modificare il percorso di installazione dei file di Skype for Business Server nella finestra di dialogo Setup. Se si installano i file di installazione in questo percorso, incluso OCSCore.msi, anche il resto dei file di Skype for Business Server verrà distribuito in questa unità. 

## <a name="to-install-the-administrative-tools"></a>Per installare gli strumenti di amministrazione

1. Eseguire l'accesso come amministratore locale (requisito minimo) al computer in cui si desidera installare gli strumenti di amministrazione. Se è stato eseguito l'accesso come utente standard in Windows e il controllo dell'account utente è abilitato, verrà richiesto l'amministratore locale o un nome utente e una password equivalenti al dominio.
2. Individuare il supporto di installazione nel computer e quindi fare doppio clic su \Setup\amd64\Setup.exe.
3. Se viene richiesto di installare Microsoft Visual C++ distribuibili, fare clic su **Sì**.
4. Nella pagina Percorso di installazione fare clic su **OK**. Sostituire il percorso indicato con un altro percorso o un'altra unità se è necessario installare i file in una diversa posizione.

    > [!Important]
    > Se l'organizzazione richiede l'individuazione di Internet Information Services (IIS) e di tutti i servizi Web in un'unità diversa dall'unità di sistema, è possibile modificare il percorso di installazione dei file di Skype for Business Server nella finestra di dialogo Setup. Se si installano i file di installazione in questo percorso, incluso OCSCore.msi, anche il resto dei file di Skype for Business Server verrà distribuito nell'unità. 

5. Nella pagina Contratto di licenza con l'utente finale leggere le condizioni di licenza, fare clic su **Accetto** e quindi su **OK**. Questo passaggio è obbligatorio per poter continuare.
6. Nella pagina distribuzione guidata fare clic su **installa strumenti di amministrazione**. 
7. Al termine dell'installazione fare clic su **Esci**.

Utilizzare le procedure seguenti per aprire strumenti di amministrazione per la distribuzione, la configurazione o la risoluzione dei problemi relativi alla topologia di Skype for Business Server.

- [Distribuzione guidata](#deployment-wizard)
- [Generatore di topologie](#topology-builder) 
- [Pannello di controllo di Skype for Business Server](#skype-for-business-server-control-panel)
- [Skype for Business Server Management Shell](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Distribuzione guidata

Utilizzare la procedura seguente per avviare la distribuzione guidata localmente per aggiungere o rimuovere i file dei componenti.

**Per avviare la distribuzione guidata di Skype for Business Server**

1. Accedere al computer in cui è installata la distribuzione guidata di Skype for Business Server come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.
2. Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server** e quindi fare clic su **Skype for Business Server Deployment Wizard**.


## <a name="topology-builder"></a>Strumento di generazione topologia 

Utilizzare la procedura seguente per aprire il generatore di topologie per definire i server che si desidera distribuire nella topologia di Skype for Business Server.

**Per aprire il generatore di topologie di Skype for Business Server per progettare la topologia**

1. Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.
    > [!NOTE]
    > È possibile definire una topologia utilizzando un account membro del gruppo degli utenti locali, ma per leggere, pubblicare o abilitare una topologia, necessaria per installare Skype for Business Server in un server, è necessario utilizzare un account membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e che disponga di autorizzazioni di controllo completo (ovvero , lettura, scrittura e modifica) sulla condivisione file da utilizzare per l'archivio file di archiviazione in modo che generatore di topologie sia in grado di configurare l'elenco di controllo di accesso discrezionale necessario o un account con diritti utente equivalenti.
 
2. Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server** e quindi su **Generatore di topologie di Skype for Business Server**.

## <a name="skype-for-business-server-control-panel"></a>Pannello di controllo di Skype for Business Server 

Utilizzare una delle procedure seguenti per aprire il pannello di controllo di Skype for Business Server per gestire la configurazione di server, utenti, client e dispositivi nell'ambiente.

> [!NOTE]
> È possibile utilizzare un account utente assegnato al ruolo CsAdministrator per eseguire qualsiasi attività nel pannello di controllo di Skype for Business Server. È possibile utilizzare altri ruoli per accedere al pannello di controllo di Skype for Business Server per eseguire attività amministrative specifiche, a seconda dell'attività che è necessario eseguire. Ad esempio, è possibile utilizzare CSArchivingAdministrator per amministrare l'archiviazione nel pannello di controllo di Skype for Business Server. Per informazioni dettagliate sui ruoli, vedere [Planning for Role-Based Access Control](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx). Per informazioni dettagliate sui ruoli che è possibile utilizzare per eseguire un'attività specifica, vedere la documentazione relativa all'attività. 

**Per aprire il pannello di controllo di Skype for Business Server da qualsiasi computer all'interno del firewall dell'organizzazione**

1. Da un account utente assegnato al ruolo CsAdministrator o a un altro ruolo con autorizzazioni e diritti utente appropriate per l'attività da eseguire, accedere a qualsiasi computer nella distribuzione interna con una risoluzione minima dello schermo pari a 1024 x 768.

    > [!IMPORTANT]
    > Se è stato configurato un URL (Uniform Resource Locator) di amministrazione semplice, è possibile accedere al pannello di controllo di Skype for Business Server da un browser Internet in esecuzione su qualsiasi computer all'interno del firewall dell'organizzazione. Per informazioni dettagliate sulla configurazione dell'URL semplice di amministrazione, vedere [Planning for Simple URLs](https://technet.microsoft.com/library/gg398287(v=ocs.15).aspx) and [Edit or Configure Simple URLs](https://technet.microsoft.com/library/gg398063(v=ocs.15).aspx). 

2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione configurato per l'organizzazione.

**Per aprire il pannello di controllo di Skype for Business Server in un computer su cui è in esecuzione Skype for Business Server**

1. Da un account utente membro del ruolo CsAdministrator o da un altro ruolo con diritti utente e autorizzazioni appropriate per l'attività da eseguire, accedere a un computer in cui è stato installato Skype for Business Server o, almeno, gli strumenti di amministrazione di Skype for Business Server. Per configurare le impostazioni, è necessario che il computer disponga di una risoluzione dello schermo minima di 1024 x 768.
2. Avviare il pannello di controllo di Skype for Business Server: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**, quindi **Skype for Business Server** e quindi fare clic su **Pannello di controllo di Skype for Business Server**.

## <a name="skype-for-business-server-management-shell"></a>Skype for Business Server Management Shell 

Utilizzare la procedura seguente per aprire la shell di gestione di Skype for Business Server per amministrare server, utenti, client e dispositivi nell'ambiente utilizzando la riga di comando.

> [!NOTE]
> È possibile utilizzare un account utente assegnato al ruolo CsAdministrator per eseguire qualsiasi attività in Skype for Business Server Management Shell. È possibile accedere utilizzando altri ruoli per eseguire attività di amministrazione specifiche, a seconda dell'attività che è necessario eseguire. È ad esempio possibile utilizzare CSArchivingAdministrator per eseguire cmdlet correlati all'amministrazione dell'archiviazione. Per informazioni dettagliate sui ruoli, vedere [Planning for Role-Based Access Control](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx). Per informazioni dettagliate sui ruoli che è possibile utilizzare per eseguire un cmdlet specifico, vedere la documentazione relativa al cmdlet.<br/><br/>È inoltre possibile eseguire alcuni cmdlet utilizzando un account utente nel gruppo RTCUniversalServerAdmins, RTCUniversalUserAdmins o RTCUniversalReadOnlyAdmins, a seconda del cmdlet. 

**Per aprire Skype for Business Server Management Shell**

Se si apre una finestra di Windows PowerShell anziché Skype for Business Server Management Shell, per impostazione predefinita non è possibile eseguire i cmdlet di Skype for Business Server. Per eseguire i cmdlet di Skype for Business Server da Windows PowerShell, al prompt dei comandi di Windows PowerShell digitare quanto segue:

`Import-Module Lync`

Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business** server e quindi su **Skype for Business Server Management Shell**.
