---
title: 'Lync Server 2013: Protezione avanzata e sicurezza di server e applicazioni'
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
ms.openlocfilehash: 42b8b9d3fc21c590bda12841cb6002987d4c0650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>Protezione avanzata e sicurezza di server e applicazioni per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-12-05_

È consigliabile indurire e proteggere il sistema operativo e le applicazioni in base alle procedure consigliate per quel componente specifico. Questa sezione descrive come indurire i server delle applicazioni e usare criteri di gruppo per implementare i blocco della sicurezza.

<div>


> [!NOTE]  
> È anche possibile indurire e proteggere i database usati per la distribuzione di Microsoft Lync Server 2013. Per informazioni dettagliate, vedere <A href="lync-server-2013-hardening-and-protecting-databases.md">indurimento e protezione dei database di Lync Server 2013</A>.



</div>

<div>

## <a name="securing-application-servers"></a>Protezione dei server applicazioni

Per i server delle applicazioni, il sistema operativo e l'applicazione devono essere induriti. Ad esempio, un computer Windows Server 2008 dedicato all'uso di Microsoft Internet Security and Acceleration (ISA) Server 2006 deve essere indurito dal sistema operativo e dal punto di vista dell'applicazione. L'obiettivo principale è ridurre al minimo il numero di servizi eseguiti e forniti dal server.

</div>

<div>

## <a name="securing-virtual-servers"></a>Protezione dei server virtuali

Gli snapshot del server virtuale contengono copie dei dischi di dati del server e contengono anche dump di dati in memoria, che possono contenere dati crittografici riservati che potrebbero portare a attacchi. Per i server di produzione implementati con la virtualizzazione, è consigliabile disabilitare tutti gli snapshot del server o gestirli in modo molto controllato. Per informazioni dettagliate sulla protezione dei server virtuali Hyper-V, vedere la guida alla sicurezza di Hyper- [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)v all'indirizzo:.

</div>

<div>

## <a name="group-policy"></a>Criteri di gruppo

In Windows Server 2008 e Windows Server 2008 R2, criteri di gruppo offre la gestione della configurazione desktop basata su directory. È possibile usare criteri di gruppo per implementare i blocco di sicurezza definendo le impostazioni di computer e utenti in un oggetto Criteri di gruppo per gli elementi seguenti:

  - Criteri basati sul Registro di sistema

  - Sicurezza

  - Installazione del software

  - Script

  - Reindirizzamento delle cartelle

  - Servizi di installazione remota

Per offrire all'amministratore un'interfaccia utente per la configurazione di queste impostazioni, i modelli amministrativi vengono forniti con le versioni del sistema operativo, i rilasci di Service Pack e alcune applicazioni, tra cui Lync Server 2013.

Il file Communicator. adm è un modello amministrativo fornito con Lync Server 2013, viene installato nella directory% windir%\\inf\\ e fornisce un'interfaccia per le impostazioni dei criteri di gruppo. Ogni impostazione in Communicator. adm corrisponde a un'impostazione nel registro di sistema che influisce sul comportamento dell'applicazione.

È possibile accedere alle impostazioni da GPedit. dll, disponibile dalla console utenti e computer di Active Directory e dalla console Gestione criteri di gruppo.

</div>

<div>

## <a name="group-policy-security-settings"></a>Impostazioni di sicurezza dei criteri di gruppo

Criteri di gruppo contiene le impostazioni di sicurezza per un GPO in configurazione computer/impostazioni di Windows/impostazioni di sicurezza quando si accede da GPedit. dll. È possibile importare modelli di sicurezza per configurare le impostazioni di sicurezza per l'oggetto Criteri di ricerca. La guida alla sicurezza di [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) windows Server 2008 e windows Server 2008 R2 Security Compliance Management Toolkit [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) contiene numerosi modelli di esempio che è possibile modificare per soddisfare le proprie esigenze.

</div>

<div>

## <a name="best-practices"></a>Procedure consigliate

  - Indurire tutti i sistemi operativi e le applicazioni del server.

  - Proteggere gli snapshot del server e migliorare la sicurezza di tutti i server virtuali.

  - Usare criteri di gruppo per implementare il blocco della sicurezza.

</div>

</div>

<span> </span>

</div>

</div>

</div>

