---
title: 'Lync Server 2013: Strumenti di gestione di Windows PowerShell e Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814253d909ff7065ccc028cf5822be7a7331a2fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Strumenti di gestione di Windows PowerShell e Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-07-20_

In Microsoft Lync Server 2013 gli strumenti di gestione vengono implementati con Windows PowerShell. Windows PowerShell include un ambiente della riga di comando, comandi specifici del prodotto e un linguaggio di scripting completo. Gli strumenti di Lync Server 2013 implementati con Windows PowerShell includono i seguenti:

  - **Generatore di topologie**. Puoi usare generatore di topologia per creare, modificare e pubblicare la topologia pianificata e convalidare la topologia prima di iniziare le installazioni del server. Quando si installa Lync Server 2013 nei singoli server, i server leggono la topologia pubblicata come parte del processo di installazione e il programma di installazione distribuisce il server come indicato nella topologia. Dopo l'installazione, le informazioni di configurazione vengono replicate automaticamente in tutti i server. I componenti possono essere aggiunti alla distribuzione solo tramite Generatore di topologia.

  - **Lync Server Management Shell**. È possibile usare Lync Server Management Shell per la gestione completa della riga di comando della distribuzione.

  - **Pannello di controllo di Lync Server**. È possibile usare l'interfaccia utente del pannello di controllo di Microsoft Lync Server 2013 per gestire le attività più comuni nella distribuzione.

Questi strumenti usano i cmdlet di Windows PowerShell per la gestione della distribuzione, tra cui quasi tutti i cmdlet specifici per il prodotto 550. I cmdlet di sicurezza inclusi in Lync Server 2013 vengono usati principalmente per gestire l'autenticazione e i diritti utente e le autorizzazioni. È disponibile un'ampia varietà di cmdlet per la gestione dell'autenticazione, inclusi i cmdlet per il certificato e l'autenticazione PIN (Personal Identification Number). Inoltre, un certo numero di cmdlet consente di usare la nuova funzionalità controllo di accesso basato sui ruoli (RBAC) per delegare il controllo amministrativo di Lync Server 2013. Per informazioni dettagliate sui cmdlet di Lync Server, vedere [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

Le funzionalità di sicurezza degli script per Windows PowerShell sono progettate in modo specifico per evitare alcuni problemi di sicurezza correlati agli script delle tecnologie meno recenti, tra cui Microsoft Visual Basic Scripting Edition (VBScript). Le caratteristiche di sicurezza di Windows PowerShell sono destinate a creare un ambiente in cui gli utenti non possono eseguire facilmente o in modo inconsapevolmente gli script. Per impostazione predefinita, le caratteristiche di sicurezza di Windows PowerShell sono abilitate. Puoi modificare lo stato di queste funzionalità per soddisfare le tue esigenze di scripting e diversi obiettivi di sicurezza. Questo non significa che la Shell rende impossibile l'esecuzione di script da parte degli utenti. La Shell rende invece difficile, per impostazione predefinita, che gli utenti eseguano gli script senza rendersene conto. Per informazioni dettagliate, vedere la pagina relativa alla [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)sicurezza degli script di Windows PowerShell.

</div>

<span> </span>

</div>

</div>

</div>

