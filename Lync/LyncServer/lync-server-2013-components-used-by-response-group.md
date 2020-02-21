---
title: 'Lync Server 2013: componenti utilizzati da Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bfefeabc1c9f64a4f1bf9fa794b269fbdcb0650
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a>Componenti utilizzati da Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-11_

L'applicazione Response Group viene abilitata automaticamente quando si distribuisce VoIP aziendale. In questa sezione vengono descritti i componenti che supportano l'applicazione Response Group.

<div>

## <a name="response-group-components"></a>Componenti di Response Group

I componenti di Microsoft Lync Server 2013 seguenti supportano l'applicazione Response Group:

  - **Application Service**   Application Service fornisce una piattaforma per la distribuzione, l'hosting e la gestione delle applicazioni di comunicazione unificata, ad esempio Response Group. Il servizio applicazione viene installato automaticamente in tutti i front end server in un pool Front end e in tutti i server Standard Edition.

  - **Response Group**   Application l'applicazione Response Group è una delle applicazioni di comunicazione unificate ospitate dal servizio applicazione. Viene incluso automaticamente quando si distribuisce Response Group. L'applicazione Response Group consente di instradare e accodare le chiamate in arrivo a gruppi di agenti.

  - **Language Pack**   è necessario un Language Pack per il supporto del riconoscimento vocale e del testo. Queste tecnologie vocali vengono usate quando si configurano messaggi, ad esempio messaggi di benvenuto o di altro tipo, nonché domande e risposte IVR (Interactive Voice Response). Per impostazione predefinita, i 26 Language Pack supportati vengono installati quando si distribuisce Lync Server 2013.

  - **I file audio vengono**utilizzati per i messaggi e la musica di attesa.   

  - ****   Il gruppo di risposta dell'archivio file utilizza l'archivio file per archiviare i file audio. Più pool di Response Group possono utilizzare la stessa istanza dell'archivio file.

  - **Strumento di configurazione di Response Group**   lo strumento di configurazione di Response Group è uno strumento basato sul Web che viene utilizzato per creare e configurare i Response Group. Lo strumento di configurazione di Response Group è incluso quando si installano i servizi Web.

  - **Pannello di controllo di Microsoft Lync Server 2013**   è possibile utilizzare il pannello di controllo di Lync Server per installare e configurare gruppi di agenti e code per i Response Group.

  - **Lync Server Management Shell**   tutte le impostazioni di Response Group possono essere configurate utilizzando i cmdlet di Lync Server Management Shell.

  - **Microsoft Lync 2013**   agenti formali (gli agenti necessari per accedere al gruppo prima che possano accettare le chiamate per il gruppo) utilizzano Lync 2013 per accedere e disconnettersi dal gruppo. Se un gruppo di agenti è configurato per gli agenti formali, gli agenti fanno clic su una voce di menu in Lync 2013 per aprire Internet Explorer e visualizzare una console di pagina Web per l'accesso e la disconnessione del gruppo.

  - ****   I servizi Web dei servizi Web sono necessari per lo strumento di configurazione di Response Group, la console di accesso e disconnessione degli agenti, il pannello di controllo di Lync Server e il servizio Web client di Response Group.

  - **Response Group client Web**   Response Group Application fornisce un servizio Web client, che può essere utilizzato da applicazioni di terze parti per recuperare informazioni sugli agenti, l'appartenenza a un gruppo di agenti, lo stato di accesso dell'agente, lo stato delle chiamate per i gruppi e i gruppi che supportano le chiamate anonime. Lync 2013 e Lync 2010 Attendant utilizzano il servizio Web client di Response Group per recuperare l'elenco dei Response Group che gli agenti possono utilizzare per effettuare chiamate anonime. Il servizio Web client viene incluso quando si installano i servizi Web.

</div>

</div>

<span> </span>

</div>

</div>

</div>

