---
title: "Lync Server 2013: personalizzazione dell'installazione del client"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customizing client installation
ms:assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204934(v=OCS.15)
ms:contentKeyID: 48184254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9491e48d107d01f86d18e8154331ef3ae7e478
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="da017-102">Personalizzazione dell'installazione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da017-102">Customizing client installation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da017-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="da017-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="da017-104">Gli amministratori aziendali possono personalizzare l'installazione di Office 2013 basato su Windows Installer (con estensione msi) usando i metodi descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="da017-104">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="da017-105">Poiché nessun singolo strumento offre tutte le opzioni di personalizzazione, è probabile che si usi una combinazione di questi metodi nella distribuzione di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="da017-105">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="da017-106">È possibile usare gli strumenti descritti nelle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="da017-106">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="da017-107">[Usare lo strumento di personalizzazione di Office in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) per personalizzare le opzioni di configurazione e le funzionalità per Lync e altre applicazioni di Office.</span><span class="sxs-lookup"><span data-stu-id="da017-107">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="da017-108">[Uso di config. XML per eseguire attività di installazione in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) per specificare il percorso del punto di installazione di rete ed eseguire l'installazione invisibile all'utente.</span><span class="sxs-lookup"><span data-stu-id="da017-108">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="da017-109">[Usare le opzioni della riga di comando di configurazione in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) per specificare il file config. XML da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="da017-109">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="da017-110">[Configurazione dei criteri di avvio del client in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) tramite lo snap-in MMC Editor oggetti Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="da017-110">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="da017-111">Ci saranno probabilmente altre opzioni che vorrai configurare mentre Distribuisci la famiglia di prodotti Office.</span><span class="sxs-lookup"><span data-stu-id="da017-111">There will probably be other options you’ll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="da017-112">Gli argomenti di questa sezione forniscono una panoramica di questi strumenti di personalizzazione e discutono considerazioni specifiche di Lync.</span><span class="sxs-lookup"><span data-stu-id="da017-112">The topics in this section give an overview of these customization tools and discuss Lync-specific considerations.</span></span> <span data-ttu-id="da017-113">Sono inclusi collegamenti alla guida dettagliata di Office per ogni strumento.</span><span class="sxs-lookup"><span data-stu-id="da017-113">Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

