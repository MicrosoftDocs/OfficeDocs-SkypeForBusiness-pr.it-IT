---
title: 'Lync Server 2013: Componenti utilizzati da Response Group'
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
ms.openlocfilehash: 81275ca027971d661d3323fbfc175c51d4f4d7d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a>Componenti utilizzati da Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-11_

L'applicazione Response Group viene abilitata automaticamente quando si distribuisce VoIP aziendale. In questa sezione vengono descritti i componenti che supportano l'applicazione Response Group.

<div>

## <a name="response-group-components"></a>Componenti di Response Group

I componenti di Microsoft Lync Server 2013 seguenti supportano l'applicazione Response Group:

  - **Application Service**   Application Service offre una piattaforma per la distribuzione, l'hosting e la gestione di applicazioni di comunicazioni unificate, ad esempio Response Group. Il servizio applicazione viene installato automaticamente in ogni server front-end in un pool Front-end e in ogni server Standard Edition.

  - **Response Group Application**   l'applicazione Response Group è una delle applicazioni di comunicazioni unificate ospitate dal servizio applicazione. Viene incluso automaticamente quando si distribuisce Response Group. L'applicazione Response Group instrada e accoda le chiamate in arrivo a gruppi di agenti.

  - **Language Pack**   è necessario un Language Pack per supportare il riconoscimento vocale e del testo. Queste tecnologie vocali vengono usate quando si configurano i messaggi, ad esempio il messaggio di benvenuto e altre richieste, e le domande e le risposte di risposta vocale interattiva (IVR). Per impostazione predefinita, i 26 Language Pack supportati vengono installati quando si distribuisce Lync Server 2013.

  - **I file audio vengono**usati per i messaggi e la musica in attesa.   

  - ****   Il gruppo di risposte archivio file Usa archivio file per archiviare i file audio. Più pool di gruppi di risposte possono usare la stessa istanza di file Store.

  - **Strumento di configurazione**   Response Group lo strumento di configurazione Response Group è uno strumento basato sul Web usato per creare e configurare i gruppi di risposta. Lo strumento di configurazione Response Group viene incluso quando si installano i servizi Web.

  - **Pannello di controllo di Microsoft Lync Server 2013**   è possibile usare il pannello di controllo di Lync Server per impostare e configurare gruppi di agenti e code per i gruppi di risposta.

  - **Lync Server Management Shell**   tutte le impostazioni dei gruppi di risposte possono essere configurate usando i cmdlet di Lync Server Management Shell.

  - ****   Gli agenti formali di Microsoft Lync 2013 (gli agenti che devono accedere al gruppo prima di poter accettare le chiamate per il gruppo) usano Lync 2013 per accedere e disconnettersi dal gruppo. Se un gruppo di agenti è configurato per gli agenti formali, gli agenti fanno clic su una voce di menu in Lync 2013 per aprire Internet Explorer e visualizzare una console della pagina Web per l'accesso e la disconnessione del gruppo.

  - ****   I servizi Web Web Services sono necessari per lo strumento di configurazione Response Group, la console di accesso e disconnessione degli agenti, il pannello di controllo di Lync Server e il servizio Web client Response Group.

  - **Response Group application client Web Service**   Response Group offre un servizio Web client, che può essere usato da applicazioni di terze parti per recuperare informazioni su agenti, appartenenza al gruppo di agenti, stato di accesso dell'agente, stato delle chiamate per i gruppi e i gruppi che supportano le chiamate anonime. Lync 2013 e Lync 2010 Attendant usano il servizio Web client Response Group per recuperare l'elenco dei gruppi di risposte che gli agenti possono usare per effettuare chiamate anonime. Il servizio Web client è incluso quando si installano i servizi Web.

</div>

</div>

<span> </span>

</div>

</div>

</div>

