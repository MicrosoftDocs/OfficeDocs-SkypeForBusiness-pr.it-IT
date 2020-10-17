---
title: 'Lync Server 2013: preparazione dello schema di Active Directory'
description: 'Lync Server 2013: preparazione dello schema di Active Directory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3df7533dcbabe278fd366b441cfd8daa83f54b23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560312"
---
# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>Preparazione dello schema di Active Directory in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-08-27_

Prima di iniziare la preparazione di servizi di dominio Active Directory, è possibile aprire i file di schema utilizzando un editor di testo, ad esempio Blocco note di Windows, oppure vedere [estensioni dello schema, classi e attributi di Active Directory utilizzati da Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) per esaminare tutte le estensioni dello schema dei servizi di dominio Active Directory che verranno modificate per Lync Server 2013. Lync Server utilizza quattro file di schema:

  - ExternalSchema. ldf, utilizzato per l'interoperabilità con Microsoft Exchange Server

  - ServerSchema. ldf, che è il file di schema principale di Lync Server 2013

  - BackCompatSchema.ldf, utilizzato per l'interoperabilità con gli eventuali componenti di versioni precedenti

  - VersionSchema.ldf, utilizzato per le informazioni sulla versione dello schema preparato

Tutti i file con estensione ldf vengono installati durante la preparazione dello schema, indipendentemente dal fatto che si stia eseguendo la migrazione da una versione precedente o eseguendo un'installazione pulita. Questi file di schema sono installati nella sequenza illustrata nell'elenco precedente e si trovano nella \\ cartella Support \\ schema sul supporto di installazione.

Le estensioni dello schema di Lync Server vengono replicate in tutti i domini, che influiscono sul traffico di rete. Eseguire la preparazione dello schema in un momento di scarso utilizzo della rete.

<div>


> [!NOTE]  
> Se è necessario aggiungere il supporto per Microsoft® Office Communicator Mobile 2007 R2 per Java e Microsoft® Office Communicator Mobile per i client mobili Nokia 1,0 alla distribuzione di Lync Server 2013, è necessario preparare lo schema di Active Directory per Microsoft Office Communications Server 2007 R2 durante l'installazione di Lync Server 2013. Per il software e la documentazione necessari, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A> .



</div>

<div>

## <a name="adsi-edit"></a>ADSI Edit

Active Directory Service Interfaces Editor (ADSI Edit) è uno strumento di amministrazione di Servizi di dominio Active Directory che consente di verificare la preparazione e la replica dello schema.

ADSI Edit viene installato per impostazione predefinita quando si installa il ruolo Servizi di dominio Active Directory per impostare un server come controller di dominio. Per Windows Server 2008 e Windows Server 2008 R2, ADSI Edit (ADSIEdit. msc) è incluso negli strumenti di amministrazione remota del server. È inoltre possibile installare Strumenti di amministrazione remota del server in server membri del dominio o in server autonomi. Il pacchetto di Strumenti di amministrazione remota del server viene copiato in tali server per impostazione predefinita durante l'installazione di Windows, ma non viene installato per impostazione predefinita. Per installare i singoli strumenti, utilizzare Server Manager. È possibile accedere ad ADSI Edit da **Strumenti di amministrazione ruoli**, **Strumenti per Servizi di dominio Active Directory**, **Strumenti di Controller di dominio Active Directory**.

Per Windows Server 2003, ADSI Edit è incluso negli strumenti di supporto. Gli strumenti di supporto sono disponibili nel CD di Windows Server 2003 nella \\ \\ cartella degli strumenti di supporto oppure è possibile scaricarli da "strumenti di supporto di windows Server 2003 Service Pack 2 32-bit" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770) . Le istruzioni per l'installazione degli strumenti di supporto del CD del prodotto sono disponibili da "installa gli strumenti di supporto di Windows" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771) . Adsiedit.dll viene automaticamente registrata quando si installano gli strumenti di supporto. Se, tuttavia, i file sono stati copiati nel computer in uso, è necessario eseguire il comando **regsvr32** per registrare il file adsiedit.dll prima di poter eseguire lo strumento.

</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Esecuzione della preparazione dello schema di Active Directory in Lync Server 2013](lync-server-2013-running-schema-preparation.md)

  - [Verifica della replica dello schema di Active Directory in Lync Server 2013](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Preparazione della foresta per Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Preparazione dei domini per Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

