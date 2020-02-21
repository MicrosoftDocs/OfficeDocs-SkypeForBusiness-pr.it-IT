---
title: 'Lync Server 2013: utilizzo dello strumento di personalizzazione di Office'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c55cfa8fd795feeca5e265f43823c4263512211f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a><span data-ttu-id="2a8be-102">Utilizzo dello strumento di personalizzazione di Office in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a8be-102">Using the Office Customization Tool (OCT) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a8be-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2a8be-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2a8be-104">Lo Strumento di personalizzazione di Office fa parte del programma di installazione ed è lo strumento consigliato per molte personalizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2a8be-104">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="2a8be-105">Tramite questo strumento, è possibile personalizzare Office e salvare le personalizzazioni in un file di configurazione dell'installazione con estensione msp.</span><span class="sxs-lookup"><span data-stu-id="2a8be-105">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="2a8be-106">Il file viene inserito nella cartella Aggiornamenti nella posizione di installazione dalla rete.</span><span class="sxs-lookup"><span data-stu-id="2a8be-106">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="2a8be-107">Quando si installa Office, il programma di installazione cerca un file di configurazione dell'installazione nella cartella Aggiornamenti e applica le personalizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2a8be-107">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="2a8be-108">La cartella Updates può essere utilizzata solo per distribuire gli aggiornamenti software durante un'installazione iniziale di Office 2013.</span><span class="sxs-lookup"><span data-stu-id="2a8be-108">The Updates folder can be used only to deploy software updates during an initial installation of Office 2013.</span></span>

<span data-ttu-id="2a8be-109">Lo Strumento di personalizzazione di Office fa parte dell'installazione ed è incluso nelle versioni multilicenza del prodotto.</span><span class="sxs-lookup"><span data-stu-id="2a8be-109">The OCT is part of setup and it is included in volume license versions of the product.</span></span> <span data-ttu-id="2a8be-110">È possibile eseguire lo strumento di `setup.exe /admin` personalizzazione di Office digitando dalla riga di comando dalla radice del punto di installazione di rete che contiene i file di origine di 2013.</span><span class="sxs-lookup"><span data-stu-id="2a8be-110">You run the OCT by typing `setup.exe /admin` at the command line from the root of the network installation point that contains the Office 2013 source files.</span></span> <span data-ttu-id="2a8be-111">Ad esempio, utilizzare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2a8be-111">For example, use the following:</span></span>

`\\server\share\Office15\setup.exe /admin`

<span data-ttu-id="2a8be-112">Gli amministratori utilizzano questo strumento per creare un file di configurazione dell'installazione con estensione msp.</span><span class="sxs-lookup"><span data-stu-id="2a8be-112">Administrators use the OCT to create a setup customization .msp file.</span></span> <span data-ttu-id="2a8be-113">Come in Microsoft Office 2010 OCT, gli amministratori possono personalizzare le aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a8be-113">As in the Microsoft Office 2010 OCT, administrators can customize the following areas:</span></span>

  - <span data-ttu-id="2a8be-114">**Programma di installazione** Utilizzato per specificare il percorso di installazione predefinito sul client e il nome dell'organizzazione predefinito, origini di installazione di rete aggiuntive, codice Product Key, contratto di licenza con l'utente finale, livello di visualizzazione, versioni precedenti di Office da rimuovere, programmi personalizzati da eseguire durante l'installazione, impostazioni di sicurezza e proprietà del programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="2a8be-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>

  - <span data-ttu-id="2a8be-115">**Caratteristiche** Utilizzato per configurare le impostazioni utente e per personalizzare la modalità di installazione delle caratteristiche di Office.</span><span class="sxs-lookup"><span data-stu-id="2a8be-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="2a8be-116">Gli amministratori possono utilizzare lo Strumento di personalizzazione di Office per specificare valori predefiniti iniziali delle impostazioni delle applicazioni Office per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2a8be-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="2a8be-117">Gli utenti possono modificare la maggior parte delle impostazioni dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="2a8be-117">Users can modify most of the settings after the installation.</span></span>

  - <span data-ttu-id="2a8be-118">**Contenuto aggiuntivo** Utilizzato per aggiungere o rimuovere file, aggiungere o rimuovere voci del registro di sistema e configurare i collegamenti.</span><span class="sxs-lookup"><span data-stu-id="2a8be-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>

  - <span data-ttu-id="2a8be-119">**Outlook** Utilizzato per personalizzare il profilo Outlook predefinito di un utente, specificare le impostazioni di Exchange, aggiungere account, rimuovere account ed esportare le impostazioni\\e specificare i gruppi di invio/ricezione.</span><span class="sxs-lookup"><span data-stu-id="2a8be-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\\Receive groups.</span></span>

<span data-ttu-id="2a8be-120">Per informazioni sullo strumento di personalizzazione di <https://go.microsoft.com/fwlink/p/?linkid=267516>Office, vedere.</span><span class="sxs-lookup"><span data-stu-id="2a8be-120">For information about the OCT, see <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

