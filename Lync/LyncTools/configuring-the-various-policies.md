---
title: Configurazione dei vari criteri
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6316a1027de963cefea6c0c76051f09cb5d33538
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a>Configurazione dei vari criteri

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-24_

<div>

## <a name="configuring-the-various-policies"></a>Configurazione dei vari criteri

Ecco i vari criteri che è possibile configurare nella topologia di Lync Server 2013, prima di eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013.

<div>

## <a name="configuring-the-archiving-policy"></a>Configurazione dei criteri di archiviazione

Vedere lo script di esempio ArchivingPolicy. ps1. È necessario usare questo script solo se un server di archiviazione è distribuito nella topologia. Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per l' [archiviazione e il monitoraggio dei cmdlet in Lync server 2013](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a>Configurazione dei criteri di conferenza

Vedere lo script di esempio MeetingPolicy. ps1. Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per i servizi di [conferenza Web in Lync server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-contacts-policy"></a>Configurazione dei criteri per i contatti

Vedere l'esempio ContactsPolicy. ps1. Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i [cmdlet di messaggistica istantanea e presenza in Lync server 2013](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-federation-policy"></a>Configurazione dei criteri federativi

Vedere l'esempio FederationPolicy. ps1. Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet [Edge Server nei cmdlet di Lync server 2013](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\)) e [federativo e Access esterno in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a>Configurazione dei criteri di controllo dell'ammissione alle chiamate

Vedere l'esempio BandwidthPolicy. ps1. Per informazioni dettagliate, vedere la panoramica della documentazione di Lync Server 2013 sul [controllo di ammissione delle chiamate in Lync server 2013](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\)) e la guida per i cmdlet per il [controllo dell'ammissione alle chiamate in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a>Configurazione delle regole di routing vocale

Vedere l'esempio RoutingRules. ps1. Quando si configurano le regole di routing vocale, prendere nota del contesto telefonico (ovvero/location profile o/SimpleName) e dei codici di area interni/esterni, in modo da poterli specificare quando si creano utenti e durante la configurazione di LyncPerfTool (in particolare per PSTN-UC e UC-PSTN). Ad esempio, il parametro SimpleName nella chiamata al cmdlet **New-CsDialPlan** nell'esempio RoutingRules. ps1 deve essere usato per il valore LocationProfile nella figura seguente di UserProfileGenerator. exe.

![Regola per le route vocali di esempio.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Regola per le route vocali di esempio.")

Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i [cmdlet Enterprise Voice in Lync server 2013](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a>Configurazione dell'applicazione Supervisore conferenza

Vedere l'esempio ConferenceAutoAttendantConfiguration. ps1. Prendere nota del numero di telefono di ConferencingAutoAttendant (1121111111, per impostazione predefinita), in modo da poterlo digitare nello strumento di configurazione dello strumento LyncPerf per la generazione della configurazione.

![Configurazione dell'applicazione Operatore Conferenza](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configurazione dell'applicazione Operatore Conferenza")

Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per i servizi di [conferenza Web in Lync server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)) e i [cmdlet di conferenza telefonica con accesso esterno in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a>Configurazione del servizio di parcheggio delle chiamate di Lync Server

Il parcheggio delle chiamate è disabilitato per impostazione predefinita. Vedere l'esempio CallParkConfiguration. ps1. Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i [cmdlet delle applicazioni di Call Park in Lync server 2013](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-emergency-calls"></a>Configurazione delle chiamate di emergenza

Eseguire la procedura seguente per configurare i test di stress e prestazioni per le chiamate di emergenza.

1.  Configurare una route vocale per le chiamate di emergenza. Vedere lo script RoutingRules. ps1 sotto il commento "Route E911 to PSTN" per un esempio di configurazione di questa route vocale.
    
    <div>
    

    > [!WARNING]  
    > Il comando di esempio in RoutingRules. ps1 contiene un modello di numero che include il numero 119 anziché 911. È consigliabile evitare di usare 911 (o il numero di emergenza locale effettivo) per evitare chiamate accidentali agli operatori di emergenza locali durante i test di carico. Questa configurazione è solo per scopi di simulazione.

    
    </div>

2.  Configurare gli indirizzi compilando i valori della scheda **LIS** in UserProvisioningTool, come illustrato nella figura seguente.
    
    ![Configurazione del servizio Informazioni percorso.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configurazione del servizio Informazioni percorso.")  

3.  Fare clic su **genera file di configurazione LIS**.

4.  Vengono generati i file CSV per porte, subnet, switch e punti di accesso wireless (WAP) e un file XML per lo strumento di ricerca dello stress e delle prestazioni di Lync Server 2013. I file CSV devono essere usati come input (nella stessa cartella) durante la configurazione del servizio Information Service (LIS) con lo script LisConfiguration. ps1. Sposta il file Locations0. XML generato nella stessa cartella dello strumento eseguibile di 2013 (LyncPerfTool. exe) di Lync Server, che eseguirà gli scenari del profilo di posizione (dial plan).

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a>Creazione, abilitazione, configurazione e disabilitazione degli utenti

Prima di eseguire gli script seguenti, è consigliabile creare tutti gli utenti. Seguire le istruzioni in [creare utenti e contatti](create-users-and-contacts.md) per creare utenti. Per informazioni dettagliate, vedere la documentazione del cmdlet Lync Server 2013 per i cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\))e [Disable-CsUser](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) .

</div>

<div>

## <a name="configuring-response-group-application"></a>Configurazione dell'applicazione Response Group

Vedere l'esempio ResponseGroupConfiguration. ps1. Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i [cmdlet delle applicazioni di Response Group in Lync server 2013](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\)). Per esaminare la configurazione dell'applicazione Response Group, `https://<poolfqdn>/RgsConfig/`vedere, come illustrato nella figura seguente.

![Strumento di configurazione di Response Group.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "Strumento di configurazione di Response Group.")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

