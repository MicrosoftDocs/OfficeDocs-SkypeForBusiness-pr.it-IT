---
title: 'Lync Server 2013: uso dello strumento di personalizzazione di Office (ott)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd9c101b9098f9a5a6ac6088740c067039921b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a><span data-ttu-id="ebf2d-102">Uso dello strumento di personalizzazione di Office (ott) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebf2d-102">Using the Office Customization Tool (OCT) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebf2d-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ebf2d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ebf2d-104">Lo strumento di personalizzazione di Office (ott) fa parte del programma di installazione ed è lo strumento consigliato per molte personalizzazioni.</span><span class="sxs-lookup"><span data-stu-id="ebf2d-104">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="ebf2d-105">Usando lo strumento di personalizzazione di Office, è possibile personalizzare l'ufficio e salvare le personalizzazioni in un file msp di personalizzazione della configurazione.</span><span class="sxs-lookup"><span data-stu-id="ebf2d-105">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="ebf2d-106">Si inserisce il file nella cartella Updates nel punto di installazione della rete.</span><span class="sxs-lookup"><span data-stu-id="ebf2d-106">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="ebf2d-107">Durante l'installazione di Office, la configurazione Cerca un file di personalizzazione della configurazione nella cartella Updates e applica le personalizzazioni.</span><span class="sxs-lookup"><span data-stu-id="ebf2d-107">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="ebf2d-108">La cartella Updates può essere usata solo per distribuire gli aggiornamenti software durante un'installazione iniziale di Office 2013.</span><span class="sxs-lookup"><span data-stu-id="ebf2d-108">The Updates folder can be used only to deploy software updates during an initial installation of Office 2013.</span></span>

<span data-ttu-id="ebf2d-109">Lo strumento di personalizzazione di ottobre fa parte della configurazione ed è incluso nelle versioni con contratto multilicenza del prodotto.</span><span class="sxs-lookup"><span data-stu-id="ebf2d-109">The OCT is part of setup and it is included in volume license versions of the product.</span></span> <span data-ttu-id="ebf2d-110">Per eseguire lo strumento di personalizzazione `setup.exe /admin` di Office, digitare alla riga di comando dalla radice del punto di installazione di rete che contiene i file di origine di 2013.</span><span class="sxs-lookup"><span data-stu-id="ebf2d-110">You run the OCT by typing `setup.exe /admin` at the command line from the root of the network installation point that contains the Office 2013 source files.</span></span> <span data-ttu-id="ebf2d-111">Ad esempio, usare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ebf2d-111">For example, use the following:</span></span>

`\\server\share\Office15\setup.exe /admin`

<span data-ttu-id="ebf2d-112">Gli amministratori usano lo strumento di personalizzazione di ottobre per creare un file msp di personalizzazione della configurazione.</span><span class="sxs-lookup"><span data-stu-id="ebf2d-112">Administrators use the OCT to create a setup customization .msp file.</span></span> <span data-ttu-id="ebf2d-113">Come in Microsoft Office 2010 OCT, gli amministratori possono personalizzare le aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="ebf2d-113">As in the Microsoft Office 2010 OCT, administrators can customize the following areas:</span></span>

  - <span data-ttu-id="ebf2d-114">**Configurazione** Usato per specificare il percorso di installazione predefinito nel client e il nome dell'organizzazione predefinito, altre origini di installazione di rete, codice Product Key, contratto di licenza con l'utente finale, livello di visualizzazione, versioni precedenti di Office da rimuovere, programmi personalizzati da eseguire durante l'installazione, le impostazioni di sicurezza e le proprietà di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ebf2d-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>

  - <span data-ttu-id="ebf2d-115">**Caratteristiche** Consente di configurare le impostazioni utente e di personalizzare la modalità di installazione delle funzionalità di Office.</span><span class="sxs-lookup"><span data-stu-id="ebf2d-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="ebf2d-116">Gli amministratori possono usare lo strumento di personalizzazione di Office per specificare i valori predefiniti iniziali delle impostazioni dell'applicazione per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="ebf2d-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="ebf2d-117">Gli utenti possono modificare la maggior parte delle impostazioni dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="ebf2d-117">Users can modify most of the settings after the installation.</span></span>

  - <span data-ttu-id="ebf2d-118">**Contenuto aggiuntivo** Consente di aggiungere o rimuovere file, aggiungere o rimuovere voci del registro di sistema e configurare i tasti di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="ebf2d-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>

  - <span data-ttu-id="ebf2d-119">**Outlook** Usato per personalizzare il profilo di Outlook predefinito di un utente, specificare le impostazioni di Exchange, aggiungere account, rimuovere gli account ed esportare\\le impostazioni e specificare i gruppi di invio.</span><span class="sxs-lookup"><span data-stu-id="ebf2d-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\\Receive groups.</span></span>

<span data-ttu-id="ebf2d-120">Per informazioni sullo strumento di personalizzazione di <http://go.microsoft.com/fwlink/p/?linkid=267516>ottobre, vedere.</span><span class="sxs-lookup"><span data-stu-id="ebf2d-120">For information about the OCT, see <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

