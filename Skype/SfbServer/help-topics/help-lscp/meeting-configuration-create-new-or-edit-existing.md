---
title: Configurazione della riunione creare nuovi o modificarne uno esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: Le impostazioni di configurazione delle riunioni definiscono l'esperienza di partecipazione degli utenti per le conferenze pianificate dall'utente. Queste impostazioni si applicano solo alle riunioni pianificate. Non si applicano a riunioni ad-hoc create facendo clic sull'opzione Meet Now nel client.
ms.openlocfilehash: dc37e3d76a81a09fe2cbd2407f4d3a2dff3d703e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803936"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="7e861-105">Configurazione riunione: crearne una nuova o modificarne una esistente</span><span class="sxs-lookup"><span data-stu-id="7e861-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="7e861-106">Le impostazioni di configurazione delle riunioni definiscono l'esperienza di partecipazione degli utenti per le conferenze pianificate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7e861-106">Meeting configuration settings define the user join experience for conferences scheduled by users.</span></span> <span data-ttu-id="7e861-107">Queste impostazioni si applicano solo alle riunioni pianificate.</span><span class="sxs-lookup"><span data-stu-id="7e861-107">These settings only apply to scheduled meetings.</span></span> <span data-ttu-id="7e861-108">Non si applicano a riunioni ad-hoc create facendo clic sull'opzione **Meet Now** nel client.</span><span class="sxs-lookup"><span data-stu-id="7e861-108">They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="7e861-109">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="7e861-109">UI Reference</span></span>

<span data-ttu-id="7e861-110">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="7e861-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="7e861-111">**Ambito** Identifica l'ambito della configurazione della riunione che si sta creando o modificando: globale, sito o pool.</span><span class="sxs-lookup"><span data-stu-id="7e861-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="7e861-112">**Nome** Le configurazioni delle riunioni sono denominate per impostazione predefinita e il nome non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="7e861-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="7e861-113">**Lobby di bypass per i chiamanti PSTN** Selezionare questa casella di controllo per consentire l'accesso automatico agli utenti che eseguono la chiamata alla conferenza tramite una linea telefonica PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="7e861-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="7e861-114">Deselezionare la casella di controllo per instradare i chiamanti PSTN alla sala di attesa della conferenza, dove rimangono in attesa fino a quando un relatore non concede loro l'accesso alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7e861-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="7e861-115">**Designa come relatore** Selezionare la categoria di utenti (oltre all'organizzatore della riunione) che vengono automaticamente designati come relatori quando partecipano a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="7e861-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="7e861-116">Indipendentemente da questa impostazione, i relatori possono essere designati in modo esplicito come tali quando viene pianificata la conferenza oppure possono essere promossi in modo esplicito a relatori durante la conferenza.</span><span class="sxs-lookup"><span data-stu-id="7e861-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="7e861-117">Le opzioni sono:</span><span class="sxs-lookup"><span data-stu-id="7e861-117">The options are:</span></span>

  - <span data-ttu-id="7e861-118">**Nessuna** Selezionare questa opzione se nessun altro è definito automaticamente come relatore.</span><span class="sxs-lookup"><span data-stu-id="7e861-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="7e861-119">**Azienda** Selezionare questa opzione per designare automaticamente solo i membri dell'organizzazione come relatori.</span><span class="sxs-lookup"><span data-stu-id="7e861-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="7e861-120">**Tutti gli utenti** Selezionare questa opzione per designare automaticamente tutti i relatori.</span><span class="sxs-lookup"><span data-stu-id="7e861-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="7e861-121">**Tipo di conferenza assegnato per impostazione predefinita** Questa impostazione consente di controllare se Outlook Conferencing AddIn Pianifica sempre le conferenze utilizzando la conferenza assegnata dall'organizzatore, il che significa che le conferenze pianificate hanno sempre lo stesso URL di join e le stesse informazioni audio.</span><span class="sxs-lookup"><span data-stu-id="7e861-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="7e861-122">Selezionare questa casella di controllo per fare in modo che le conferenze pianificate usino sempre lo stesso URL per la partecipazione.</span><span class="sxs-lookup"><span data-stu-id="7e861-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="7e861-123">Deselezionare la casella di controllo per usare un URL per la partecipazione diverso per ogni conferenza.</span><span class="sxs-lookup"><span data-stu-id="7e861-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="7e861-124">**Ammetti gli utenti anonimi per impostazione predefinita** Selezionare questa casella di controllo se agli utenti anonimi, ovvero non autenticati, sono consentiti di partecipare a conferenze per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7e861-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="7e861-125">Deselezionare la casella di controllo se, per impostazione predefinita, agli utenti anonimi non è consentito partecipare alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="7e861-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="7e861-126">**URL logo** Digitare l'URL che contiene l'immagine da utilizzare per gli inviti alla conferenza personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7e861-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="7e861-127">**URL della Guida** Digitare l'URL di un sito Web in cui gli utenti possono ottenere assistenza per la partecipazione alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7e861-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="7e861-128">**URL di testo legale** Digitare l'URL di un sito Web contenente le informazioni legali e le dichiarazioni di non responsabilità per la conferenza.</span><span class="sxs-lookup"><span data-stu-id="7e861-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="7e861-129">**Testo del piè** di pagina personalizzato Digitare il testo da utilizzare per gli inviti alla conferenza personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7e861-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="7e861-130">Per informazioni dettagliate sull'utilizzo di configurazioni riunioni, vedere [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="7e861-130">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span> <span data-ttu-id="7e861-131">Per informazioni dettagliate sull'impostazione delle configurazioni per riunioni di grandi dimensioni, vedere [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7e861-131">For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


