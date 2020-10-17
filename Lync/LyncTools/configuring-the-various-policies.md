---
title: Configurazione dei diversi criteri
description: Configurazione dei diversi criteri.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 746d299ac605c7dfe89a957246d47309dfbc0a5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548842"
---
# <a name="configuring-the-various-policies"></a>Configurazione dei diversi criteri

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-24_

<div>

Di seguito sono riportati i diversi criteri che è possibile configurare nella topologia di Lync Server 2013, prima di eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013.

<div>

## <a name="configuring-the-archiving-policy"></a>Configurazione dei criteri di archiviazione

Vedere lo script di esempio ArchivingPolicy.ps1. È necessario utilizzare questo script solo se è stato distribuito un server di archiviazione nella topologia. Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per l' [archiviazione e il monitoraggio dei cmdlet in Lync server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a>Configurazione dei criteri di conferenza

Vedere lo script di esempio MeetingPolicy.ps1. Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per le [conferenze Web in Lync server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-contacts-policy"></a>Configurazione dei criteri contatti

Vedere l'esempio ContactsPolicy.ps1. Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per la [messaggistica istantanea e la presenza in Lync server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-federation-policy"></a>Configurazione dei criteri di Federazione

Vedere l'esempio FederationPolicy.ps1. Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet del [server perimetrale in Lync server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) e i [cmdlet di Federazione e accesso esterno in Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a>Configurazione del criterio di controllo di ammissione di chiamata

Vedere l'esempio BandwidthPolicy.ps1. Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 [Panoramica del controllo di ammissione di chiamata in Lync server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) e la guida per i cmdlet per il [controllo di ammissione di chiamata in Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a>Configurazione delle regole di routing vocale

Vedere l'esempio RoutingRules.ps1. Quando si configurano le regole di routing vocale, prendere nota del contesto telefonico (ovvero/location profile o/SimpleName) e dei codici di area interni/esterni in modo da poterli specificare quando si creano gli utenti e durante la configurazione di LyncPerfTool (in particolare per PSTN-UC e UC-PSTN). Ad esempio, il parametro SimpleName nella chiamata al cmdlet **New-CsDialPlan** nell'esempio RoutingRules.ps1 deve essere utilizzato per il valore LocationProfile nella figura seguente di UserProfileGenerator.exe.

![Regola di routing vocale di esempio.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Regola di routing vocale di esempio.")

Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet di [VoIP aziendale in Lync server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a>Configurazione dell'applicazione Operatore Conferenza

Vedere l'esempio ConferenceAutoAttendantConfiguration.ps1. Prendere nota del numero di telefono di ConferencingAutoAttendant (1121111111, per impostazione predefinita), in modo che sia possibile digitarlo nello strumento di configurazione dello strumento di LyncPerf per la generazione di configurazione.

![Configurazione dell'applicazione Operatore Conferenza](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configurazione dell'applicazione Operatore Conferenza")

Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per le [conferenze Web in Lync server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) e i cmdlet per le conferenze telefoniche con [accesso esterno in Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a>Configurazione del servizio parcheggio di chiamata di Lync Server

Il parcheggio di chiamata è disabilitato per impostazione predefinita. Vedere l'esempio CallParkConfiguration.ps1. Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida del cmdlet per i [cmdlet dell'applicazione Parcheggio di chiamata in Lync server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-emergency-calls"></a>Configurazione delle chiamate di emergenza

Eseguire la procedura seguente per configurare i test di stress e prestazioni per le chiamate di emergenza.

1.  Impostare una route vocale per le chiamate di emergenza. Vedere lo script RoutingRules.ps1 nel commento "Route E911 to PSTN" per un esempio di configurazione di questa route vocale.
    
    <div>
    

    > [!WARNING]  
    > Il comando di esempio in RoutingRules.ps1 ha un modello di numero che include il numero 119 anziché 911. È consigliabile evitare di usare 911 (o il numero di emergenza locale effettivo) per impedire chiamate accidentali agli operatori di emergenza locali durante il test di carico. Questa configurazione è solo per scopi di simulazione.

    
    </div>

2.  Configurare gli indirizzi compilando i valori della scheda **LIS** in UserProvisioningTool, come illustrato nella figura seguente.
    
    ![Configurazione del servizio informazioni percorso.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configurazione del servizio informazioni percorso.")  

3.  Fare clic su **genera file di configurazione LIS**.

4.  Vengono generati i file CSV per porte, subnet, commutatori e punti di accesso wireless (WAP) e un file XML per lo strumento di stress e prestazioni di Lync Server 2013. I file CSV devono essere utilizzati come input (nella stessa cartella) durante la configurazione del servizio informazioni percorso (LIS) con lo script LisConfiguration.ps1. Spostare il file di Locations0.xml generato nella stessa cartella in cui si trova l'eseguibile dello strumento di stress e prestazioni di Lync Server 2013 (LyncPerfTool.exe), che eseguirà gli scenari del profilo percorso (dial plan).

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a>Creazione, abilitazione, configurazione e disabilitazione degli utenti

Prima di eseguire gli script seguenti, è consigliabile creare tutti gli utenti. Seguire le istruzioni riportate in [creare utenti e contatti](create-users-and-contacts.md) per creare gli utenti. Per informazioni dettagliate, vedere la documentazione relativa ai cmdlet di Lync Server 2013 per i cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))e [Disable-CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) .

</div>

<div>

## <a name="configuring-response-group-application"></a>Configurazione dell'applicazione Response Group

Vedere l'esempio ResponseGroupConfiguration.ps1. Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per le [applicazioni di Response Group in Lync server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)). Per esaminare la configurazione dell'applicazione Response Group, vedere `https://<poolfqdn>/RgsConfig/` , come illustrato nella figura seguente.

![Strumento di configurazione di Response Group.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "Strumento di configurazione di Response Group.")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

