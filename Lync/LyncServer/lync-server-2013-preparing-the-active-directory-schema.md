---
title: 'Lync Server 2013: Preparazione dello schema di Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5479bfbb0774ddd68015de470de082f0cc185b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>Preparazione dello schema di Active Directory in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-08-27_

Prima di iniziare la preparazione dei servizi di dominio Active Directory, è possibile aprire i file di schema usando un editor di testo, come il blocco note di Windows, oppure vedere le [estensioni, le classi e gli attributi di uno schema di Active Directory usati da Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) per esaminare tutte le estensioni dello schema di servizi di dominio Active Directory che verranno modificate per lync Server 2013. Lync Server usa quattro file di schema:

  - ExternalSchema. ldf, usato per l'interoperabilità con Microsoft Exchange Server

  - ServerSchema. ldf, che è il file di schema 2013 principale di Lync Server

  - BackCompatSchema. ldf, usato per l'interoperabilità con tutti i componenti di versioni precedenti

  - VersionSchema. ldf, usato per le informazioni sulla versione dello schema preparato

Tutti i file con estensione ldf vengono installati durante la preparazione dello schema, indipendentemente dal fatto che si stia eseguendo la migrazione da una versione precedente o sia stata eseguita un'installazione pulita. Questi file di schema vengono installati nella sequenza visualizzata nell'elenco precedente e si trovano nella cartella dello \\schema\\di supporto nel supporto di installazione.

Le estensioni dello schema di Lync Server vengono replicate in tutti i domini, che influiscono sul traffico di rete. Eseguire la preparazione dello schema in un momento in cui l'utilizzo della rete è basso.

<div>


> [!NOTE]  
> Se è necessario aggiungere il supporto per Microsoft® Office Communicator Mobile 2007 R2 per Java e Microsoft® Office Communicator Mobile per i client mobili Nokia 1,0 alla distribuzione di Lync Server 2013, è necessario preparare lo schema Active Directory per Microsoft Office Communications Server 2007 R2 durante l'installazione di Lync Server 2013. Per il software e la documentazione necessari, <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>vedere.



</div>

<div>

## <a name="adsi-edit"></a>Modifica ADSI

Active Directory Service Interfaces Editor (ADSI Edit) è uno strumento di amministrazione AD DS che puoi usare per verificare la preparazione e la replica dello schema.

ADSI Edit viene installato per impostazione predefinita quando si installa il ruolo di servizi di dominio Active Directory per rendere un server un domain controller. Per Windows Server 2008 e Windows Server 2008 R2, ADSI Edit (ADSIEdit. msc) è incluso negli strumenti di amministrazione del server remoto. È anche possibile installare i server di amministrazione remota in Domain Member o server autonomi. Il pacchetto di amministrazione remota viene copiato in questi server per impostazione predefinita quando si installa Windows, ma non viene installato per impostazione predefinita. Si installano singoli strumenti tramite Server Manager. ADSI Edit è incluso in **strumenti amministrazione ruoli**, **strumenti servizi di dominio Active Directory**, **strumenti Domain controller di Active Directory**.

Per Windows Server 2003, ADSI Edit è incluso negli strumenti di supporto. Gli strumenti di supporto sono disponibili nel CD di Windows Server 2003 nella \\cartella\\strumenti di supporto oppure è possibile scaricarli da "strumenti di supporto di Windows server 2003 Service Pack 2 32-bit [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770)" at. Le istruzioni per l'installazione degli strumenti di supporto dal CD del prodotto sono disponibili in [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)"installare gli strumenti di supporto di Windows". ADSIEdit. dll viene registrato automaticamente quando si installano gli strumenti di supporto. Se invece i file sono stati copiati nel computer, è necessario eseguire il comando **regsvr32** per registrare il file adsiedit. dll prima di poter eseguire lo strumento.

</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Esecuzione della preparazione dello schema in Lync Server 2013](lync-server-2013-running-schema-preparation.md)

  - [Verifica della replica dello schema in Lync Server 2013](lync-server-2013-verifying-schema-replication.md)

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

