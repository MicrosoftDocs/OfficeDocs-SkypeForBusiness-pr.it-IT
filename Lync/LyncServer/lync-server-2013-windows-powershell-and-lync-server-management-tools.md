---
title: 'Lync Server 2013: strumenti di gestione di Windows PowerShell e Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c24a94bf74b2ecf911179d64691e95153acceeeb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Strumenti di gestione di Windows PowerShell e Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-07-20_

In Microsoft Lync Server 2013, gli strumenti di gestione vengono implementati tramite Windows PowerShell. Windows PowerShell include un ambiente della riga di comando, comandi specifici del prodotto e un linguaggio di script completo. Gli strumenti di Lync Server 2013 implementati tramite Windows PowerShell includono i seguenti:

  - **Generatore di topologie**. Per creare, modificare e pubblicare la topologia pianificata, è possibile utilizzare Generatore di topologie e convalidare la topologia prima di iniziare le installazioni del server. Quando si installa Lync Server 2013 nei singoli server, i server leggono la topologia pubblicata come parte del processo di installazione e il server viene distribuito come indicato nella topologia. Dopo l'installazione, le informazioni di configurazione vengono replicate automaticamente in tutti i server. I componenti possono essere aggiunti alla distribuzione solo tramite Generatore di topologie.

  - **Lync Server Management Shell**. È possibile utilizzare Lync Server Management Shell per la gestione completa della riga di comando della distribuzione.

  - **Pannello di controllo di Lync Server**. È possibile utilizzare l'interfaccia utente del pannello di controllo di Microsoft Lync Server 2013 per gestire le attività più comuni nella distribuzione.

Questi strumenti utilizzano i cmdlet di Windows PowerShell per la gestione della distribuzione, inclusi quasi 550 cmdlet specifici del prodotto. I cmdlet di sicurezza inclusi in Lync Server 2013 vengono utilizzati principalmente per gestire l'autenticazione e i diritti utente e le autorizzazioni. È disponibile un'ampia gamma di cmdlet per la gestione dell'autenticazione, inclusi i cmdlet per l'autenticazione tramite certificato e PIN. Inoltre, un certo numero di cmdlet consentono di utilizzare la nuova funzionalità di controllo di accesso basato sui ruoli (RBAC) per delegare il controllo amministrativo di Lync Server 2013. Per informazioni dettagliate sui cmdlet di Lync Server, vedere [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

Le funzionalità per la sicurezza degli script per Windows PowerShell sono progettate appositamente per evitare alcuni dei problemi di sicurezza correlati agli script di tecnologie meno recenti, incluso Microsoft Visual Basic Scripting Edition (VBScript). Le funzionalità di sicurezza di Windows PowerShell sono pensate per creare un ambiente in cui gli utenti non possono eseguire gli script facilmente o in modo inconsapevole. Le funzionalità di sicurezza di Windows PowerShell sono abilitate per impostazione predefinita. È possibile modificare lo stato di queste funzionalità per adattarle alle esigenze specifiche per gli script e a un'ampia gamma di obiettivi per la sicurezza. Ciò non significa che l'esecuzione degli script sia resa impossibile dalla shell. L'obiettivo, per impostazione predefinita, è invece quello di rendere difficile per gli utenti eseguire script senza esserne consapevoli. Per informazioni dettagliate, vedere Windows PowerShell script Security [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145)at.

</div>

<span> </span>

</div>

</div>

</div>

