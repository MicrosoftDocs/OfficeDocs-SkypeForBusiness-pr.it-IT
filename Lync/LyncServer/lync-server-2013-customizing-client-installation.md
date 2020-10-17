---
title: "Lync Server 2013: personalizzazione dell'installazione del client"
description: "Lync Server 2013: personalizzazione dell'installazione del client."
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
ms.openlocfilehash: 8dd1942c298ccbc8b6a2950baf4f24cc2f797a92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561142"
---
# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="60c3d-103">Personalizzazione dell'installazione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60c3d-103">Customizing client installation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60c3d-104">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="60c3d-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="60c3d-105">Gli amministratori dell'organizzazione possono personalizzare l'installazione di Office 2013 basato su Windows Installer (con estensione msi) utilizzando i metodi illustrati in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="60c3d-105">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="60c3d-106">Poiché nessun singolo strumento fornisce tutte le opzioni di personalizzazione, è probabile che venga utilizzata una combinazione di questi metodi nella distribuzione di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="60c3d-106">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="60c3d-107">È possibile che vengano utilizzati come minimo gli strumenti descritti nelle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="60c3d-107">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="60c3d-108">[Utilizzo dello strumento di personalizzazione di Office in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) per personalizzare le opzioni di installazione e le funzionalità di Lync e di altre applicazioni di Office.</span><span class="sxs-lookup"><span data-stu-id="60c3d-108">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="60c3d-109">[Utilizzo di Config.xml per eseguire le attività di installazione in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) per specificare il percorso del punto di installazione di rete ed eseguire l'installazione invisibile all'utente.</span><span class="sxs-lookup"><span data-stu-id="60c3d-109">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="60c3d-110">[Utilizzo delle opzioni della riga di comando del programma di installazione in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) per specificare il file di Config.xml da utilizzare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="60c3d-110">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="60c3d-111">[Configurazione dei criteri di avvio del client in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) mediante lo snap-in MMC Editor oggetti Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="60c3d-111">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="60c3d-p102">È probabile che risulti necessario configurare altre opzioni durante la distribuzione della famiglia di prodotti Office. Negli argomenti in questa sezione viene offerta una panoramica di questi strumenti di personalizzazione e vengono presentate alcune considerazioni specifiche per Lync. Sono inclusi collegamenti alle informazioni dettagliate della Guida di Office per ogni strumento.</span><span class="sxs-lookup"><span data-stu-id="60c3d-p102">There will probably be other options you’ll want to configure as you deploy the Office suite of products. The topics in this section give an overview of these customization tools and discuss Lync-specific considerations. Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

