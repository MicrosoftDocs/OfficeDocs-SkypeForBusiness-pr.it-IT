---
title: 'Lync Server 2013: indurimento e protezione di server e applicazioni'
description: 'Lync Server 2013: indurimento e protezione di server e applicazioni.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed1205439208dfdadf5396b976d5d4876fb0aa24
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567442"
---
# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>Indurimento e protezione di server e applicazioni per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-12-05_

È consigliabile applicare protezione avanzata e sicurezza al sistema operativo e alle applicazioni in base alle procedure consigliate per il componente specifico. In questa sezione viene descritto come applicare protezione avanzata ai server applicazioni e utilizzare Criteri di gruppo per implementare blocchi di sicurezza.

<div>


> [!NOTE]  
> È inoltre possibile indurire e proteggere i database utilizzati per la distribuzione di Microsoft Lync Server 2013. Per informazioni dettagliate, vedere <A href="lync-server-2013-hardening-and-protecting-databases.md">hardening and Protecting the databases of Lync Server 2013</A>.



</div>

<div>

## <a name="securing-application-servers"></a>Protezione dei server applicazioni

Per i server applicazioni, è consigliabile applicare protezione avanzata al sistema operativo e all'applicazione. A un computer Windows Server 2008 dedicato all'esecuzione di Microsoft Internet Security and Acceleration (ISA) Server 2006, ad esempio, è consigliabile applicare protezione avanzata dal punto di vista del sistema operativo e delle applicazioni. La riduzione del numero di servizi in esecuzione e forniti dal server deve costituire l'obiettivo principale.

</div>

<div>

## <a name="securing-virtual-servers"></a>Protezione dei server virtuali

Gli snapshot dei server virtuali contengono copie dei dischi dati del server e dump di dati in memoria, che possono a loro volta contenere dati di crittografia sensibili e pertanto provocare attacchi. Per i server di produzione implementati tramite la virtualizzazione, è consigliabile disabilitare tutti gli snapshot dei server o gestirli in modo molto rigoroso. Per informazioni dettagliate sulla protezione dei server virtuali Hyper-V, vedere la guida alla sicurezza di Hyper-V all'indirizzo: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176) .

</div>

<div>

## <a name="group-policy"></a>Criteri di gruppo

In Windows Server 2008 e Windows Server 2008 R2 Criteri di gruppo offre gestione della configurazione desktop basata su directory. È possibile utilizzare Criteri di gruppo per implementare blocchi di sicurezza definendo impostazioni computer e utente all'interno di un oggetto Criteri di gruppo per gli elementi seguenti:

  - Criteri basati sul Registro di sistema

  - Sicurezza

  - Installazione software

  - Script

  - Reindirizzamento cartelle

  - Servizi di installazione remota

Per fornire a un'interfaccia utente per l'amministratore la configurazione di queste impostazioni, i modelli amministrativi vengono forniti con versioni del sistema operativo, rilasci del Service Pack e alcune applicazioni, incluso Lync Server 2013.

Il file Communicator. adm è un modello amministrativo fornito con Lync Server 2013, viene installato nella directory% windir% \\ inf \\ e fornisce un'interfaccia per le impostazioni di criteri di gruppo. Ogni impostazione contenuta nel file Communicator.adm corrisponde a un'impostazione nel Registro di sistema che influisce sul comportamento dell'applicazione.

È possibile accedere alle impostazioni da GPedit.dll, disponibile dalla console Utenti e computer di Active Directory e da Console Gestione Criteri di gruppo.

</div>

<div>

## <a name="group-policy-security-settings"></a>Impostazioni di sicurezza di Criteri di gruppo

Criteri di gruppo contiene impostazioni di sicurezza per un oggetto Criteri di gruppo in Configurazione computer/Impostazioni di Windows/Impostazioni protezione quando si accede da GPedit.dll. È possibile importare modelli di sicurezza per configurare le impostazioni di sicurezza per l'oggetto Criteri di gruppo. La guida alla sicurezza di Windows Server 2008 [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) e Windows server 2008 R2 Security Compliance Management Toolkit [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) contengono una serie di modelli di esempio che è possibile modificare per soddisfare le proprie esigenze.

</div>

<div>

## <a name="best-practices"></a>Procedure consigliate

  - Applicare protezione avanzata a tutti i sistemi operativi e le applicazioni server.

  - Proteggere gli snapshot dei server e migliorare la sicurezza di tutti i server virtuali.

  - Utilizzare Criteri di gruppo per implementare blocchi di sicurezza.

</div>

</div>

<span> </span>

</div>

</div>

</div>

