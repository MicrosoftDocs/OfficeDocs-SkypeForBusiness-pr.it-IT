---
title: 'Lync Server 2013: risoluzione dei problemi relativi al pannello di controllo di Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 943f2ab5f0fe808d1bf5e10cf8b451ac1df2575b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a>Risoluzione dei problemi relativi al pannello di controllo di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-07-28_

Questo argomento fornisce informazioni e procedure che consentono di risolvere i problemi di accesso al pannello di controllo di Lync Server 2013.

<div>

## <a name="internet-browser-requirements"></a>Requisiti per i browser Internet

Il pannello di controllo di Lync Server richiede che il plug-in del browser di Microsoft Silverlight sia installato versione 4.0.50524.0 o ultima versione. Se Silverlight non è installato o se è installata una versione precedente, seguire le istruzioni del messaggio per installare la versione richiesta.

<div>


> [!NOTE]  
> Altri requisiti software per il pannello di controllo di Lync Server riguardano il sistema operativo in cui è possibile installare il pannello di controllo di Lync Server e tutti gli altri strumenti di amministrazione di Lync Server 2013. Per informazioni dettagliate, vedere <A href="lync-server-2013-server-and-tools-operating-system-support.md">supporto dei sistemi operativi server e strumenti in Lync server 2013</A> nella documentazione relativa al supporto tecnico.



</div>

Se il browser Internet blocca l'installazione di Silverlight a causa di considerazioni sulla sicurezza, aggiungere l'URL (Uniform Resource Locator) che apre il pannello di controllo di Lync Server all'elenco dei siti attendibili. Nelle impostazioni di sicurezza di Internet Explorer verificare che i **controlli ActiveX e i plug-** in siano impostati su **Enabled**. Per informazioni dettagliate, [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060)vedere. Verificare inoltre che il browser sia configurato per l'uso di SSL 3,0.

Se il browser Internet è configurato per l'uso di un server proxy, verificare che il browser sia configurato per ignorare il server proxy per i siti che vengono rilevati automaticamente come siti interni. In alternativa, aggiungere l'indirizzo all'elenco delle eccezioni del browser nelle impostazioni di configurazione del server proxy.

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>Requisiti per i record DNS e i certificati per l'URL di accesso amministrativo

Se è stato configurato un semplice URL per accedere al pannello di controllo di Lync Server, è anche stato configurato il record di risorse DNS (Domain Name System) (A) statico e il certificato necessario per l'uso di tale URL di accesso amministrativo. Se si modifica l'URL di base in qualsiasi momento, assicurarsi che la modifica venga applicata al record DNS appropriato e al certificato e che si esegua *Enable-CsComputer* su ogni Director e front end server per registrare la modifica. Per informazioni dettagliate, vedere gli argomenti seguenti nella documentazione relativa alla pianificazione:

  - [Pianificazione degli URL semplici in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

  - [Requisiti DNS per gli URL semplici in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Requisiti dei certificati per i server interni in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

Per le procedure dettagliate per la configurazione dell'URL di accesso amministrativo, vedere [modificare o configurare URL semplici in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Requisiti di Internet Information Services (IIS)

Il pannello di controllo di Lync Server è uno dei componenti di Lync Server 2013 che richiedono Internet Information Services (IIS). In particolare, assicurati che il reindirizzamento HTTP e le caratteristiche di autenticazione di Windows siano abilitati e che il servizio pubblicazione sul Web (W3SVC) sia in uso.

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>Dipendenza del servizio di pubblicazione in tutto il mondo (servizio Windows)

Quando il servizio pubblicazione sul Web viene interrotto, non è possibile accedere al pannello di controllo di Lync Server. Puoi riavviare il servizio usando Microsoft Management Console (MMC) di Windows Services.

**Per avviare il servizio pubblicazione sul Web**

1.  Accedere al computer in cui è installato il servizio pubblicazione sul Web come parte di Internet Information Services (IIS).

2.  Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **Servizi**.

3.  Fare clic con il pulsante destro del mouse su **World Wide Web Publishing Service**e quindi scegliere **Start**.

</div>

<div>

## <a name="application-pool-mode"></a>Modalità pool di applicazioni

Configurare IIS in modo che il pool di applicazioni di CsManagementAppPool usi l'account del servizio di rete come identità del modello di processo.

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>Diritti utente e autorizzazioni

È necessario accedere al pannello di controllo di Lync Server usando un account di dominio membro del gruppo CsAdministrator o usando un account a cui sono stati delegati i diritti e le autorizzazioni degli utenti. Non è possibile accedere al pannello di controllo di Lync Server usando un account del computer locale. Per informazioni dettagliate sulla delega delle attività amministrative tramite il controllo di accesso basato sui ruoli (RBAC), vedere [pianificazione del controllo di accesso basato sui ruoli in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) nella documentazione relativa alla pianificazione.

Se si usa un URL semplice per accedere al pannello di controllo di Lync Server, verificare che i server Web vengano aggiunti ai gruppi RTCUniversalServerAdmins e RTCUniversalUserAdmins.

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

