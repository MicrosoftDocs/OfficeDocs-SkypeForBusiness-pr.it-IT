---
title: "Lync Server 2013: Processo di distribuzione per l'integrazione della messaggistica unificata di Exchange ospitata"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6269efd85261c702c77568fac67c96034ba01a71
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>Processo di distribuzione per l'integrazione della messaggistica unificata di Exchange ospitata con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-25_

Una pianificazione efficace per l'integrazione di Lync Server 2013 con messaggistica unificata di Exchange ospitata richiede che si prenda in considerazione le operazioni seguenti:

  - Prerequisiti per l'integrazione di Lync Server 2013 con UM ospitata di Exchange

  - Passaggi necessari durante il processo di integrazione

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>Prerequisiti di distribuzione per l'integrazione con la messaggistica unificata di Exchange ospitata

Prima di iniziare il processo di integrazione, è necessario che sia già stato distribuito Lync Server 2013 (almeno un pool Front-end o un server Standard Edition), un server perimetrale e i client Lync 2013 o Lync 2010.

</div>

<div>

## <a name="integration-process"></a>Processo di integrazione

La tabella seguente offre una panoramica del processo di integrazione della messaggistica unificata di Exchange ospitata. Per informazioni dettagliate sulla procedura di distribuzione, vedere [fornire agli utenti di Lync Server 2013 la segreteria telefonica di Exchange ospitata](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) nella documentazione relativa alla distribuzione.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Passaggi</th>
<th>Diritti e autorizzazioni</th>
<th>Documentazione di distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurare il server perimetrale.</p></td>
<td><ol>
<li><p>Configurare il server perimetrale per la federazione.</p></li>
<li><p>Replicare manualmente i dati nel server perimetrale.</p></li>
<li><p>Configurare il provider di hosting nel server perimetrale.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configurare il server perimetrale per l'integrazione con la messaggistica unificata di Exchange ospitata</a></p></td>
</tr>
<tr class="even">
<td><p>Configurare i criteri di segreteria telefonica ospitata.</p></td>
<td><ol>
<li><p>Modificare i criteri di segreteria telefonica ospitata globale o creare un nuovo criterio di segreteria telefonica ospitata con ambito sito o per utente.</p></li>
<li><p>Per i criteri con ambito per utente, assegnare i criteri agli utenti o ai gruppi.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Gestire i criteri di segreteria telefonica ospitata in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Abilitare gli utenti per la segreteria telefonica ospitata.</p></td>
<td><ul>
<li><p>Configurare gli account utente per gli utenti le cui cassette postali si trovano in un servizio ospitato di Exchange.</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Abilitare gli utenti per la segreteria telefonica ospitata in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurare gli oggetti contatto ospitati.</p></td>
<td><ol>
<li><p>Creare oggetti contatto di operatore automatico per la messaggistica unificata di Exchange ospitata.</p></li>
<li><p>Creare oggetti contatto di accesso del Sottoscrittore per UM di Exchange ospitata.</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> Per creare, modificare o rimuovere oggetti contatto, l'utente che esegue il cmdlet New-CsExUmContact, Set-CsExUmContact o Remove-CsExUmContact deve avere l'autorizzazione corretta per l'unità organizzativa di Active Directory in cui sono archiviati i nuovi oggetti contatto. Questa autorizzazione può essere concessa eseguendo il cmdlet Grant-CsOUPermission. Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Creare oggetti contatto per la messaggistica unificata di Exchange ospitata in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

