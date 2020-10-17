---
title: 'Lync Server 2013: risoluzione dei problemi del pannello di controllo di Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7da23bc56d18b1b5e6235551f7b99cc15e658fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535933"
---
# <a name="troubleshooting-lync-server-2013-control-panel"></a>Risoluzione dei problemi relativi al Pannello di controllo di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-07-28_

In questo argomento vengono fornite informazioni e procedure che consentono di risolvere i problemi relativi all'accesso al pannello di controllo di Lync Server 2013.

<div>

## <a name="internet-browser-requirements"></a>Requisiti per il browser Internet

Per il pannello di controllo di Lync Server è necessario che sia installato il plug-in del browser Microsoft Silverlight 4.0.50524.0 o versione più recente. Se Silverlight non è installato o se è installata una versione precedente, seguire le istruzioni riportate nel messaggio per installare la versione desiderata.

<div>


> [!NOTE]  
> Altri requisiti software per il pannello di controllo di Lync Server sono relativi al sistema operativo in cui è possibile installare il pannello di controllo di Lync Server e tutti gli altri strumenti di amministrazione di Lync Server 2013. Per informazioni dettagliate, vedere <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and Tools Operating System Support in Lync server 2013</A> nella documentazione relativa alla supportabilità.



</div>

Se il browser Internet blocca l'installazione di Silverlight a causa di considerazioni sulla sicurezza, aggiungere l'URL (Uniform Resource Locator) che apre il pannello di controllo di Lync Server all'elenco dei siti attendibili. Nelle impostazioni di sicurezza di Internet Explorer assicurarsi che l'opzione **Esegui controlli ActiveX e plug-in** sia impostata su **Attivato**. Per informazioni dettagliate, vedere [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060) . Assicurarsi inoltre che il browser sia configurato per l'utilizzo di SSL 3.0.

Se il browser Internet è configurato per l'utilizzo di un server proxy, verificare che il browser sia configurato per il bypass del server proxy per i siti rilevati automaticamente come siti interni. In alternativa aggiungere l'indirizzo all'elenco delle eccezioni del browser nelle impostazioni di configurazione del server proxy.

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>Requisiti per record DNS e certificati per l'URL di accesso amministrativo

Se è stato configurato un URL semplice per accedere al pannello di controllo di Lync Server, è necessario configurare anche il record di risorse host DNS (A) e il certificato necessari per l'utilizzo di tale URL di accesso amministrativo. Se si modifica l'URL di base in qualsiasi momento, verificare che la modifica venga riflessa nel record e nel certificato DNS appropriato e che venga eseguito il metodo *Enable-CsComputer* in ogni Director e front end server per registrare la modifica. Per informazioni dettagliate, vedere gli argomenti seguenti nella documentazione relativa alla pianificazione:

  - [Pianificazione degli URL semplici in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

  - [Requisiti DNS per gli URL semplici in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Requisiti dei certificati per i server interni in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

Per le procedure dettagliate per la configurazione dell'URL di accesso amministrativo, vedere [Edit or Configure Simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Requisiti relativi a IIS (Internet Information Services)

Il pannello di controllo di Lync Server è uno dei componenti di Lync Server 2013 che richiede Internet Information Services (IIS). In particolare, assicurarsi che siano abilitate le funzionalità di reindirizzamento HTTP e di autenticazione di Windows e che sia in esecuzione il servizio Pubblicazione sul Web (W3SVC).

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>Dipendenze per il servizio Pubblicazione sul Web di Windows

Quando il servizio pubblicazione sul Web viene interrotto, non è possibile accedere al pannello di controllo di Lync Server. È possibile riavviare il servizio tramite la console MMC (Microsoft Management Console) Servizi di Windows.

**Per avviare il servizio Pubblicazione sul Web**

1.  Accedere al computer in cui è installato il servizio pubblicazione sul Web come parte di Internet Information Services (IIS).

2.  Fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **Servizi**.

3.  Fare clic con il pulsante destro del mouse su **Servizio Pubblicazione sul Web** e quindi fare clic su **Avvia**.

</div>

<div>

## <a name="application-pool-mode"></a>Modalità del pool di applicazioni

Configurare IIS in modo che il pool di applicazioni CsManagementAppPool utilizzi l'account Servizio di rete come identità del modello di elaborazione.

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>Diritti utente e autorizzazioni

Per accedere al pannello di controllo di Lync Server, è necessario utilizzare un account di dominio membro del gruppo CsAdministrator oppure un account a cui sono stati delegati diritti utente e autorizzazioni. Non è possibile accedere al pannello di controllo di Lync Server utilizzando un account del computer locale. Per informazioni dettagliate sulla delega delle attività amministrative tramite il controllo di accesso basato sui ruoli (RBAC), vedere [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) nella documentazione relativa alla pianificazione.

Se si utilizza un URL semplice per accedere al pannello di controllo di Lync Server, assicurarsi che i server Web siano stati aggiunti ai gruppi RTCUniversalServerAdmins e RTCUniversalUserAdmins.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Strumenti di amministrazione di Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

