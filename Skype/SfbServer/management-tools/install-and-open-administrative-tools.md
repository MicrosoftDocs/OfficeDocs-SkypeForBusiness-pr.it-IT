---
title: Installare e aprire strumenti di amministrazione
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: In questo argomento viene descritto come installare e aprire gli strumenti di amministrazione necessari per distribuire e gestire Skype for Business.
ms.openlocfilehash: 21fc33f5e095100f9634695925e1000172742695
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848419"
---
# <a name="install-and-open-administrative-tools"></a>Installare e aprire strumenti di amministrazione

In questo argomento viene descritto come installare gli strumenti di amministrazione necessari per distribuire e gestire Skype for Business Server. Gli strumenti di amministrazione vengono installati per impostazione predefinita in ogni server che esegue Skype for Business Server. È inoltre possibile installare gli strumenti di amministrazione in altri computer, ad esempio console di amministrazione dedicate. È consigliabile installare gli strumenti di amministrazione in un computer che si trova nello stesso dominio o foresta della distribuzione di Skype for Business Server che si sta creando, per assicurarsi che i passaggi di preparazione di Servizi di dominio Active Directory siano già stati completati, in modo da consentire l'utilizzo degli strumenti di amministrazione in quel computer in un secondo momento per pubblicare la topologia. Assicurarsi inoltre di esaminare i requisiti necessari prima di installare o utilizzare gli Skype for Business Server amministrativi. Vedere la documentazione relativa ai [requisiti in Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md) [o Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Se l'organizzazione richiede di individuare Internet Information Services (IIS) e tutti i servizi Web in un'unità diversa dall'unità di sistema, è possibile modificare il percorso di installazione per i file di Skype for Business Server nella finestra di dialogo Installazione. Se si installano i file di installazione in questo percorso, incluso OCSCore.msi, anche gli altri file Skype for Business Server verranno distribuiti in questa unità. 

## <a name="to-install-the-administrative-tools"></a>Per installare gli strumenti di amministrazione

1. Eseguire l'accesso come amministratore locale (requisito minimo) al computer in cui si desidera installare gli strumenti di amministrazione. Se si è connessi come utente standard in Windows e controllo dell'account utente è abilitato, verrà richiesto all'amministratore locale o a un nome utente e una password equivalenti al dominio.
2. Individuare il supporto di installazione nel computer e quindi fare doppio clic su \Setup\amd64\Setup.exe.
3. Se viene richiesto di installare il Microsoft Visual C++ distribuibile, fare clic su **Sì.**
4. Nella pagina Percorso di installazione fare clic su **OK**. Sostituire il percorso indicato con un altro percorso o un'altra unità se è necessario installare i file in una diversa posizione.

    > [!Important]
    > Se l'organizzazione richiede di individuare Internet Information Services (IIS) e tutti i servizi Web in un'unità diversa dall'unità di sistema, è possibile modificare il percorso di installazione per i file di Skype for Business Server nella finestra di dialogo Installazione. Se si installano i file di installazione in questo percorso, incluso OCSCore.msi, anche gli altri file Skype for Business Server verranno distribuiti in questa unità. 

5. Nella pagina Contratto di licenza con l'utente finale leggere le condizioni di licenza, fare clic su **Accetto** e quindi su **OK**. Questo passaggio è obbligatorio per poter continuare.
6. Nella pagina Distribuzione guidata fare clic su **Installa strumenti di amministrazione.** 
7. Al termine dell'installazione fare clic su **Esci**.

Utilizzare le procedure seguenti per aprire gli strumenti di amministrazione per distribuire, configurare o risolvere i problemi della Skype for Business Server topologia.

- [Distribuzione guidata](#deployment-wizard)
- [Generatore di topologie](#topology-builder) 
- [Pannello di controllo di Skype for Business Server](#skype-for-business-server-control-panel)
- [Skype for Business Server Management Shell](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Distribuzione guidata

Utilizzare la procedura seguente per avviare la Distribuzione guidata in locale per aggiungere o rimuovere i file dei componenti.

**Per avviare la Skype for Business Server guidata**

1. Accedere al computer in cui è installata Skype for Business Server distribuzione guidata come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.
2. Fare **clic sul pulsante Start,** **scegliere** Tutti i programmi, **Skype for Business Server** e quindi fare clic Skype for Business Server **distribuzione guidata.**


## <a name="topology-builder"></a>Strumento di generazione topologia 

Utilizzare la procedura seguente per aprire Generatore di topologie per definire i server che si desidera distribuire nella Skype for Business Server topologia.

**Per aprire generatore Skype for Business Server per progettare la topologia**

1. Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.
    > [!NOTE]
    > È possibile definire una topologia utilizzando un account membro del gruppo Users locale, ma per leggere, pubblicare o abilitare una topologia, necessaria per installare Skype for Business Server in un server, è necessario utilizzare un account membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins,  e che dispone delle autorizzazioni di controllo completo ,ovvero lettura, scrittura e modifica, nella condivisione file che si desidera utilizzare per l'archivio file di archiviazione in modo che Generatore di topologie possa configurare l'elenco di controllo di accesso discrezionale (DACL) richiesto o un account con diritti utente equivalenti.
 
2. Avviare Generatore di topologie: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** Skype for Business Server **e** quindi Skype for Business Server Generatore **di topologie.**

## <a name="skype-for-business-server-control-panel"></a>Pannello di controllo di Skype for Business Server 

Utilizzare una delle procedure seguenti per aprire il Skype for Business Server di controllo per gestire la configurazione di server, utenti, client e dispositivi nell'ambiente.

> [!NOTE]
> È possibile utilizzare un account utente assegnato al ruolo CsAdministrator per eseguire qualsiasi attività nel Skype for Business Server Pannello di controllo. È possibile utilizzare altri ruoli per accedere al Pannello di controllo di Skype for Business Server per eseguire attività di amministrazione specifiche, a seconda dell'attività che è necessario eseguire. Ad esempio, è possibile utilizzare CSArchivingAdministrator per amministrare l'archiviazione nel Skype for Business Server di controllo. Per informazioni dettagliate sui ruoli, vedere [Planning for role-based access control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control). Per informazioni dettagliate sui ruoli che è possibile utilizzare per eseguire un'attività specifica, vedere la documentazione relativa all'attività. 

**Per aprire il Skype for Business Server di controllo da qualsiasi computer all'interno del firewall dell'organizzazione**

1. Da un account utente assegnato al ruolo CsAdministrator o a un altro ruolo con autorizzazioni e diritti utente appropriati per l'attività da eseguire, accedere a qualsiasi computer della distribuzione interna con una risoluzione dello schermo minima di 1024 x 768.

    > [!IMPORTANT]
    > Se è stato configurato un URL (Uniform Resource Locator) di amministrazione, è possibile accedere al Pannello di controllo di Skype for Business Server da un browser Internet in esecuzione su qualsiasi computer all'interno del firewall dell'organizzazione. Per informazioni dettagliate sulla configurazione dell'URL semplice di amministrazione, vedere [Planning for simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls) e [Edit or configure simple URLs.](/previous-versions/office/lync-server-2013/lync-server-2013-edit-or-configure-simple-urls) 

2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione configurato per l'organizzazione.

**Per aprire il Skype for Business Server di controllo in un computer che esegue Skype for Business Server**

1. Da un account utente membro del ruolo CsAdministrator o di un altro ruolo con autorizzazioni e diritti utente appropriati per l'attività da eseguire, accedere a un computer in cui è stato installato Skype for Business Server o, almeno, agli strumenti di amministrazione di Skype for Business Server. Per configurare le impostazioni, il computer deve avere una risoluzione dello schermo minima di 1024 x 768.
2. Start Skype for Business Server Control Panel: click **Start**, click **All Programs**, point to **Administrative Tools,** point to **Skype for Business Server**, and then click Skype for Business Server **Control Panel**.

## <a name="skype-for-business-server-management-shell"></a>Skype for Business Server Management Shell 

Utilizzare la procedura seguente per aprire Skype for Business Server Management Shell per amministrare server, utenti, client e dispositivi nell'ambiente utilizzando la riga di comando.

> [!NOTE]
> È possibile utilizzare un account utente assegnato al ruolo CsAdministrator per eseguire qualsiasi attività in Skype for Business Server Management Shell. È possibile accedere utilizzando altri ruoli per eseguire attività di amministrazione specifiche, a seconda dell'attività che è necessario eseguire. È ad esempio possibile utilizzare CSArchivingAdministrator per eseguire cmdlet correlati all'amministrazione dell'archiviazione. Per informazioni dettagliate sui ruoli, vedere [Planning for role-based access control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control). Per informazioni dettagliate sui ruoli che è possibile utilizzare per eseguire un cmdlet specifico, vedere la documentazione relativa al cmdlet.<br/><br/>È inoltre possibile eseguire alcuni cmdlet utilizzando un account utente nel gruppo RTCUniversalServerAdmins, RTCUniversalUserAdmins o RTCUniversalReadOnlyAdmins, a seconda del cmdlet. 

**Per aprire Skype for Business Server Management Shell**

Se si apre una finestra Windows PowerShell anziché Skype for Business Server Management Shell, per impostazione predefinita non è possibile eseguire Skype for Business Server cmdlet. Per eseguire i cmdlet Skype for Business Server dall'Windows PowerShell, digitare quanto segue al prompt dei Windows PowerShell comando:

`Import-Module Lync`

Avviare la Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server** e quindi fare clic su Skype for Business Server **Management Shell**.