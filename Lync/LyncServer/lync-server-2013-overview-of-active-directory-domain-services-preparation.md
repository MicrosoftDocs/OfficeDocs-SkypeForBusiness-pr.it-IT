---
title: 'Lync Server 2013: Panoramica della preparazione di Servizi di dominio Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26636846ce7b985a33af3175d51798c4c12c5ea7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Panoramica della preparazione di Servizi di dominio Active Directory in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-29_

Per preparare i servizi di dominio Active Directory per la distribuzione di Lync Server 2013, è necessario eseguire tre passaggi in una sequenza specifica.

La tabella seguente descrive i passaggi necessari per preparare Servizi di dominio Active Directory per Lync Server.

### <a name="active-directory-preparation-steps"></a>Procedura di preparazione di Active Directory

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
<th>Dove eseguire</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparazione dello schema di Active Directory in Lync Server 2013</a></p></td>
<td><p>Estende lo schema di Active Directory aggiungendo nuove classi e attributi usati da Lync Server.</p>
<p>Eseguire una sola volta per ogni foresta nella distribuzione in cui verrà distribuito Lync Server.</p></td>
<td><p>Con lo schema master nel dominio radice di ogni foresta in cui verrà distribuito Lync Server.</p>
<div>

> [!NOTE]  
> Non è necessario eseguire questo passaggio nel dominio radice se si dispone delle autorizzazioni per lo schema master, ma è necessario essere membri del gruppo amministratori schema nel dominio radice e un membro del gruppo amministratori organizzazione nello schema master. In una topologia di foresta di risorse eseguire questo passaggio solo nella foresta delle risorse, non in tutte le foreste degli utenti. In una topologia di foresta centrale eseguire questo passaggio solo nella foresta centrale, non in tutte le foreste degli utenti.


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Preparazione della foresta per Lync Server 2013</a></p></td>
<td><p>Crea le impostazioni globali e i gruppi universali usati da Lync Server.</p>
<p>Eseguire una sola volta per ogni foresta nella distribuzione in cui verrà distribuito Lync Server.</p></td>
<td><p>Nel dominio radice di ogni foresta in cui verrà distribuito Lync Server. Per eseguire questo passaggio, è necessario essere un membro del gruppo amministratori dell'organizzazione.</p>
<div>

> [!NOTE]  
> In una topologia di foresta di risorse eseguire questo passaggio solo nella foresta delle risorse, non in tutte le foreste degli utenti. In una topologia di foresta centrale eseguire questo passaggio solo nella foresta centrale, non in tutte le foreste degli utenti.


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Preparazione dei domini per Lync Server 2013</a></p></td>
<td><p>Aggiunge le autorizzazioni per gli oggetti che possono essere usati dai membri dei gruppi universali.</p>
<p>Eseguire una volta per dominio utente o dominio server.</p>
<div>

> [!NOTE]  
> Se si esegue la migrazione da Lync Server 2010 a Lync Server 2013, la distribuzione guidata potrebbe indicare che la preparazione del dominio è già stata completata. Non è necessario eseguire di nuovo la preparazione del dominio. Le autorizzazioni non sono state modificate da Lync Server 2010 a Lync Server 2013.


</div></td>
<td><p>In un server membro in ogni dominio in cui verrà distribuito Lync Server. Per eseguire questo passaggio, è necessario essere un membro del gruppo Domain Admins.</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

Lync Server 2013, ad esempio Lync Server 2010, archivia gran parte delle informazioni di configurazione nell'Central Management store invece che in servizi di dominio Active Directory, come nel caso di Office Communications Server 2007 R2. Le informazioni seguenti sono tuttavia archiviate in servizi di dominio Active Directory:

  - **Estensioni dello schema**:
    
      - Estensioni degli oggetti utente
    
      - Estensioni per le classi di Office Communications Server 2007 R2 per mantenere la compatibilità con le versioni precedenti

<!-- end list -->

  - **Dati** (archiviati nello schema esteso di Lync Server e nelle classi dello schema esistenti):
    
      - URI (Uniform Resource Identifier) SIP dell'utente e altre impostazioni utente
    
      - Oggetti contatto per applicazioni come Response Group e operatore di conferenza
    
      - Un puntatore all'archivio di gestione centrale
    
      - Account di autenticazione Kerberos (un oggetto computer facoltativo)

In Lync Server 2013 deleghi la configurazione e l'amministrazione concedendo le autorizzazioni di configurazione al gruppo universale RTCUniversalServerAdmins in modo che i membri del gruppo possano installare e attivare Lync Server 2013 in un server locale (dopo che il server è stato aggiunto al topologia, pubblicata e abilitata). Gli utenti delegati devono essere amministratori locali nel computer in cui stanno installando e attivando Lync Server 2013, ma non devono essere membri del gruppo Domain Admins. È anche possibile concedere le autorizzazioni per gli oggetti nelle unità organizzative specificate, in modo che i membri dei gruppi universali creati durante la preparazione della foresta possano accedere a tali oggetti senza essere membri del gruppo Domain Admins.

Per le nuove distribuzioni di Lync Server 2013, le impostazioni globali devono essere archiviate nel contenitore di configurazione. Se l'organizzazione esegue l'aggiornamento da una versione precedente e si hanno ancora impostazioni globali nel contenitore di sistema, il contenitore di sistema è ancora supportato.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Preparazione dello schema di Active Directory in Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
[Estensioni dello schema, classi e attributi di Active Directory utilizzati da Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[Preparazione della foresta per Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Preparazione dei domini per Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

