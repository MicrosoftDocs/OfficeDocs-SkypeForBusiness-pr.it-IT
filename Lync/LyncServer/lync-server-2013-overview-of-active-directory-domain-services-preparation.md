---
title: 'Lync Server 2013: Panoramica della preparazione di servizi di dominio Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0074b1739cd571db46fc704d4863ac4f0462c99b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500583"
---
# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Panoramica della preparazione di servizi di dominio Active Directory in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-29_

Per preparare Servizi di dominio Active Directory per la distribuzione di Lync Server 2013, è necessario eseguire tre passaggi in una sequenza specifica.

Nella tabella seguente vengono illustrati i passaggi necessari per preparare Servizi di dominio Active Directory per Lync Server.

### <a name="active-directory-preparation-steps"></a>Passaggi di preparazione di Active Directory

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Passaggio</th>
<th>Descrizione</th>
<th>Esecuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparazione dello schema di Active Directory in Lync Server 2013</a></p></td>
<td><p>Estende lo schema di Active Directory aggiungendo nuove classi e attributi utilizzati da Lync Server.</p>
<p>Eseguire una sola volta per ogni foresta nella distribuzione in cui verrà distribuito Lync Server.</p></td>
<td><p>In base al master schema nel dominio radice di ogni foresta in cui verrà distribuito Lync Server.</p>
<div>

> [!NOTE]  
> Non è necessario eseguire questo passaggio nel dominio radice se si dispone delle autorizzazioni sul master di schemi, ma è necessario essere un membro del gruppo Schema Admins nel dominio radice e un membro del gruppo Enterprise Admins nel master di schemi. In una topologia di foresta di risorse eseguire questo passaggio solo nella foresta di risorse e non nelle foreste di utenti. In una topologia di foresta centrale eseguire questo passaggio solo nella foresta centrale e non nelle foreste di utenti.


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Preparazione della foresta per Lync Server 2013</a></p></td>
<td><p>Crea le impostazioni globali e i gruppi universali utilizzati da Lync Server.</p>
<p>Eseguire una sola volta per ogni foresta nella distribuzione in cui verrà distribuito Lync Server.</p></td>
<td><p>Nel dominio radice di ogni foresta in cui verrà distribuito Lync Server. Per eseguire questo passaggio, è necessario essere un membro del gruppo Enterprise Admins.</p>
<div>

> [!NOTE]  
> In una topologia di foresta di risorse eseguire questo passaggio solo nella foresta di risorse e non nelle foreste di utenti. In una topologia di foresta centrale eseguire questo passaggio solo nella foresta centrale e non nelle foreste di utenti.


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Preparazione dei domini per Lync Server 2013</a></p></td>
<td><p>Aggiunge autorizzazioni per gli oggetti che verranno utilizzati dai membri dei gruppi universali.</p>
<p>Eseguire il passaggio una volta per ogni dominio utente o server.</p>
<div>

> [!NOTE]  
> Se si esegue la migrazione da Lync Server 2010 a Lync Server 2013, la distribuzione guidata potrebbe indicare che la preparazione del dominio è già stata completata. Non è necessario eseguire di nuovo la preparazione del dominio. Le autorizzazioni non sono state modificate da Lync Server 2010 a Lync Server 2013.


</div></td>
<td><p>Su un server membro in ogni dominio in cui verrà distribuito Lync Server. Per eseguire questo passaggio, è necessario essere un membro del gruppo Domain Admins.</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

Lync Server 2013, come Lync Server 2010, archivia molte delle informazioni di configurazione nell'archivio di gestione centrale invece che in servizi di dominio Active Directory come nel caso di Office Communications Server 2007 R2. Tuttavia, le informazioni seguenti sono archiviate in servizi di dominio Active Directory:

  - **Estensioni dello schema**:
    
      - Estensioni degli oggetti utente
    
      - Estensioni per le classi di Office Communications Server 2007 R2 per mantenere la compatibilità con le versioni precedenti

<!-- end list -->

  - **Dati** (memorizzati nello schema esteso di Lync Server e nelle classi dello schema esistenti):
    
      - URI (Uniform Resource Identifier) SIP dell'utente e altre impostazioni utente
    
      - Oggetti contatto per applicazioni quali Response Group e Operatore Conferenza
    
      - Puntatore all'archivio di gestione centrale
    
      - Account di autenticazione Kerberos (un oggetto computer facoltativo)

In Lync Server 2013, è possibile delegare l'installazione e l'amministrazione concedendo le autorizzazioni di installazione al gruppo universale RTCUniversalServerAdmins in modo che i membri di tale gruppo possano installare e attivare Lync Server 2013 su un server locale (dopo che il server è stato aggiunto alla topologia, pubblicato e abilitato). Gli utenti delegati devono essere amministratori locali nel computer in cui eseguono l'installazione e l'attivazione di Lync Server 2013, ma non devono essere membri del gruppo Domain Admins. È anche possibile concedere autorizzazioni per gli oggetti di unità organizzative specificate, in modo che i membri dei gruppi universali creati durante la preparazione della foresta possano accedere a tali oggetti senza essere membri del gruppo Domain Admins.

Per le nuove distribuzioni di Lync Server 2013, le impostazioni globali devono essere archiviate nel contenitore di configurazione. Se l'organizzazione sta eseguendo l'aggiornamento da una versione precedente e le impostazioni globali sono ancora presenti nel contenitore di sistema, il contenitore di sistema è ancora supportato.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Preparazione dello schema di Active Directory in Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
[Estensioni, classi e attributi dello schema di Active Directory utilizzati da Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[Preparazione della foresta per Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Preparazione dei domini per Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

