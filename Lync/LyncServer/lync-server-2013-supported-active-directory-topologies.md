---
title: 'Lync Server 2013: topologie di Active Directory supportate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6eb9a3db2f9b3a14726fb7ffbec05b96b15ec81
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a>Topologie di Active Directory supportate in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-10-02_

Lync Server 2013 supporta le stesse topologie di servizi di dominio Active Directory di Microsoft Lync Server 2010 e Microsoft Office Communications Server 2007 R2. Le topologie supportate sono:

  - Foresta singola con singolo dominio

  - Foresta singola con albero singolo e più domini

  - Foresta singola con più alberi e spazi dei nomi disgiunti

  - Più foreste in una topologia di foreste centralizzate

  - Più foreste in una topologia di foresta di risorse

  - Più foreste in una topologia di foresta di risorse di Lync con Exchange Online

Nella figura seguente vengono identificate le icone utilizzate nelle illustrazioni di questa sezione.

**Legenda per le illustrazioni relative alle topologie**

![Legenda per le illustrazioni relative alle topologie](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Legenda per le illustrazioni relative alle topologie")

<div>

## <a name="single-forest-single-domain"></a>Foresta singola, dominio singolo

La topologia di Active Directory più semplice supportata da Lync Server, una foresta a dominio singolo, è una topologia comune.

Nella figura seguente viene illustrata una distribuzione di Lync Server in una topologia di Active Directory a dominio singolo.

**Topologia a dominio singolo**

![Topologia a dominio singolo](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topologia a dominio singolo")

</div>

<div>

## <a name="single-forest-multiple-domains"></a>Foresta singola, più domini

Un'altra topologia di Active Directory supportata da Lync Server è una foresta singola costituita da un dominio radice e da uno o più domini figlio. In questo tipo di topologia di Active Directory, il dominio in cui si creano gli utenti può essere diverso dal dominio in cui si distribuisce Lync Server. Se però si distribuisce un pool Front End, sarà necessario distribuire tutti i Front End Server del pool in un singolo dominio. Il supporto di Lync Server per i gruppi di amministratori universali di Windows consente l'amministrazione tra domini.

Nella figura seguente viene illustrata una distribuzione in una foresta singola con più domini. In questa figura viene visualizzata un'icona dell'utente che indica il dominio in cui risiede l'account utente e la freccia punta al dominio in cui risiede il pool di Lync Server. Gli account utente includono i seguenti:

  - Account utente all'interno dello stesso dominio del pool di Lync Server

  - Account utente in un dominio diverso dal pool di Lync Server

  - Account utente in un dominio figlio del dominio con il pool di Lync Server

**Foresta singola con più domini**

![Foresta singola con più domini](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Foresta singola con più domini")

</div>

<div>

## <a name="single-forest-multiple-trees"></a>Foresta singola, più alberi

Una topologia di foresta a più alberi è costituita da due o più domini che definiscono strutture ad albero indipendenti e spazi dei nomi di Active Directory separati.

Nella figura seguente viene illustrata una foresta singola con più alberi. In questa figura, un'icona dell'utente Visualizza il dominio in cui è ospitato l'account utente, una linea continua che punta a un pool di Lync Server che risiede nello stesso dominio o in un altro, e una linea tratteggiata punta al pool di Lync Server che risiede in un albero diverso. Gli account utente includono i seguenti:

  - Account utente all'interno dello stesso dominio del pool di Lync Server

  - Account utente in un dominio diverso da (ma lo stesso albero di) il pool di Lync Server

  - Account utente in un albero diverso dal pool di Lync Server

**Foresta singola con più alberi**

![Foresta singola con più alberi](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Foresta singola con più alberi")

</div>

<div>

## <a name="multiple-forests-central-forest"></a>Più foreste, foresta centralizzata

Lync Server supporta più insiemi di strutture configurati in una topologia a foresta centralizzata. Le topologie della foresta centrale utilizzano gli oggetti contatto nella foresta centrale per rappresentare gli utenti nelle altre foreste. La foresta centrale ospita anche account utente per tutti gli utenti della foresta. Un prodotto di sincronizzazione della directory, ad esempio Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gestisce il ciclo di vita degli account utente all'interno di l'organizzazione: quando viene creato un nuovo account utente in uno dei boschi o un account utente viene eliminato da una foresta, il prodotto di sincronizzazione della directory Sincronizza il contatto corrispondente nella foresta centrale.

Una foresta centralizzata presenta i vantaggi seguenti:

  - I server che eseguono Lync Server sono centralizzati all'interno di una singola foresta.

  - Gli utenti possono cercare altri utenti e comunicare con loro in qualsiasi foresta.

  - Gli utenti possono visualizzare la presenza di altri utenti in qualsiasi foresta.

  - Il prodotto di sincronizzazione della directory automatizza l'aggiunta e l'eliminazione di oggetti contatto nella foresta centralizzata durante la creazione o la rimozione di account utente.

Nella figura seguente viene illustrata una topologia a foresta centralizzata. In questa figura, esistono relazioni di trust bidirezionali tra il dominio che ospita Lync Server, che si trova nella foresta centrale, e ogni dominio solo utente, che si trova in una foresta separata. Non è necessario estendere lo schema nelle foreste degli utenti separate.

**Topologia a foresta centralizzata**

![Topologia a foresta centralizzata](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topologia a foresta centralizzata")

</div>

<div>

## <a name="multiple-forests-resource-forest"></a>Più foreste, foresta delle risorse

In una topologia con foresta di risorse, una foresta è dedicata all'esecuzione di applicazioni server, ad esempio Microsoft Exchange Server e Lync Server. La foresta delle risorse ospita le applicazioni server e una rappresentazione sincronizzata dell'oggetto utente attivo, ma non contiene alcun account utente abilitato per l'accesso. La foresta delle risorse funge da ambiente dei servizi condivisi per le altre foreste in cui risiedono gli oggetti utente. Le foreste degli utenti presentano una relazione di trust a livello di foresta con la foresta delle risorse. Quando si distribuisce Lync Server in questo tipo di topologia, è possibile creare un oggetto utente disabilitato nella foresta di risorse per ogni account utente nelle foreste di utenti. Se Microsoft Exchange è già distribuito nella foresta di risorse, potrebbero esistere già gli account utente disabilitati. Un prodotto di sincronizzazione della directory, come MIIS, Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gestisce il ciclo di vita degli account utente. Quando un nuovo account utente viene creato in una delle foreste degli utenti o un account utente viene eliminato da una foresta, il prodotto di sincronizzazione della directory sincronizza la rappresentazione dell'utente corrispondente nella foresta delle risorse.

Questa topologia può essere utilizzata per fornire un'infrastruttura condivisa per i servizi in organizzazioni che gestiscono più foreste o per separare l'amministrazione degli oggetti di Active Directory da un'altra amministrazione. Si tratta della scelta più frequente da parte delle società che hanno la necessità di isolare l'amministrazione di Active Directory per motivi di sicurezza.

Questa topologia offre il vantaggio di limitare la necessità di estendere lo schema di Active Directory a una singola foresta, ovvero la foresta delle risorse.

Nella figura seguente viene illustrata la topologia con foresta delle risorse.

**Topologia con foresta delle risorse**

![Topologia della foresta di risorse di Active Directory](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Topologia della foresta di risorse di Active Directory")

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a>Più foreste in una topologia di foresta di risorse di Lync con Exchange Online

In questa topologia, una o più foreste si trovano in locale e sono dedicate all'hosting degli account utente di Active Directory. La foresta di risorse si trova fuori sede ed è gestita da un provider di hosting di terze parti. La foresta di risorse contiene solo la distribuzione di Lync Server e una replica sincronizzata degli account utente dalla foresta degli account utente locali. Non contiene account utente abilitati per l'accesso. Exchange è distribuito in una foresta di account utente locale integrata insieme a Exchange Online (ibrido) oppure i servizi di posta elettronica per gli account utente locali sono forniti esclusivamente da Exchange Online.

La foresta di risorse funge da ambiente di servizi condivisi per le foreste di Active Directory locali in cui risiedono gli oggetti utente. Le foreste degli account utente dispongono di una relazione di trust a livello di foresta unidirezionale con la foresta di risorse. Quando si distribuisce Lync Server in questo tipo di topologia, è possibile creare un oggetto utente disabilitato nella foresta di risorse per ogni account utente nelle foreste di utenti. Un prodotto di sincronizzazione della directory, come MIIS, Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gestisce il ciclo di vita degli account utente. Quando un nuovo account utente viene creato in una delle foreste degli utenti o un account utente viene eliminato da una foresta, il prodotto di sincronizzazione della directory sincronizza la rappresentazione dell'utente corrispondente nella foresta delle risorse. Per ulteriori informazioni sulla configurazione di una distribuzione a più foreste, vedere [Deploying Lync in a multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](https://go.microsoft.com/fwlink/p/?linkid=513216).

</div>

</div>

<span> </span>

</div>

</div>

</div>

