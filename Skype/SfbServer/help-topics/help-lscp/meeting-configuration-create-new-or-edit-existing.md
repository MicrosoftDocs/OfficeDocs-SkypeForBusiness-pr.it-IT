---
title: Configurazione riunione Crea nuovo o Modifica esistente
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
description: Le impostazioni di configurazione delle riunioni definiscono l'esperienza di partecipazione degli utenti per le conferenze pianificate dagli utenti. Queste impostazioni si applicano solo alle riunioni pianificate. Non si applicano alle riunioni ad hoc create facendo clic sull'opzione Riunione ora nel client.
ms.openlocfilehash: 21cc12cd025edfc573e1e2f21ed08181f1a0c926
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099672"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="14e20-105">Configurazione riunione: crearne una nuova o modificarne una esistente</span><span class="sxs-lookup"><span data-stu-id="14e20-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="14e20-106">Le impostazioni di configurazione delle riunioni definiscono l'esperienza di partecipazione degli utenti per le conferenze pianificate dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="14e20-106">Meeting configuration settings define the user join experience for conferences scheduled by users.</span></span> <span data-ttu-id="14e20-107">Queste impostazioni si applicano solo alle riunioni pianificate.</span><span class="sxs-lookup"><span data-stu-id="14e20-107">These settings only apply to scheduled meetings.</span></span> <span data-ttu-id="14e20-108">Non si applicano alle riunioni ad hoc create facendo clic sull'opzione **Riunione** ora nel client.</span><span class="sxs-lookup"><span data-stu-id="14e20-108">They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="14e20-109">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="14e20-109">UI Reference</span></span>

<span data-ttu-id="14e20-110">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="14e20-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="14e20-111">**Ambito** Identifica l'ambito della configurazione di riunione che si sta creando o modificando: globale, sito o pool.</span><span class="sxs-lookup"><span data-stu-id="14e20-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="14e20-112">**Nome** Le configurazioni riunione sono denominate per impostazione predefinita e il nome non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="14e20-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="14e20-113">**I chiamanti PSTN ignorano la sala di attesa** Selezionare questa casella di controllo per ammettere automaticamente gli utenti che stanno componendo la conferenza tramite una linea telefonica PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="14e20-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="14e20-114">Deselezionare la casella di controllo per instradare i chiamanti PSTN alla sala di attesa della conferenza, dove rimangono in attesa fino a quando un relatore non concede loro l'accesso alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="14e20-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="14e20-115">**Designare come relatore** Selezionare la categoria di utenti (oltre all'organizzatore della riunione) che vengono automaticamente designati come relatori quando aderiscono a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="14e20-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="14e20-116">Indipendentemente da questa impostazione, i relatori possono essere designati in modo esplicito come tali quando viene pianificata la conferenza oppure possono essere promossi in modo esplicito a relatori durante la conferenza.</span><span class="sxs-lookup"><span data-stu-id="14e20-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="14e20-117">Le opzioni sono:</span><span class="sxs-lookup"><span data-stu-id="14e20-117">The options are:</span></span>

  - <span data-ttu-id="14e20-118">**Nessuno** Selezionare questa opzione se nessuno diverso dall'organizzatore viene designato automaticamente come relatore.</span><span class="sxs-lookup"><span data-stu-id="14e20-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="14e20-119">**Società** Selezionare questa opzione per designare automaticamente solo i membri dell'organizzazione come relatori.</span><span class="sxs-lookup"><span data-stu-id="14e20-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="14e20-120">**Tutti** Selezionare questa opzione per designare automaticamente chiunque come relatore.</span><span class="sxs-lookup"><span data-stu-id="14e20-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="14e20-121">**Tipo di conferenza assegnato per impostazione predefinita** Questa impostazione controlla se il componente aggiuntivo per conferenze di Outlook pianifica sempre le conferenze utilizzando la conferenza assegnata dall'organizzatore, il che significa che le conferenze pianificate hanno sempre lo stesso URL di partecipazione e le stesse informazioni audio.</span><span class="sxs-lookup"><span data-stu-id="14e20-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="14e20-122">Selezionare questa casella di controllo per fare in modo che le conferenze pianificate usino sempre lo stesso URL per la partecipazione.</span><span class="sxs-lookup"><span data-stu-id="14e20-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="14e20-123">Deselezionare la casella di controllo per usare un URL per la partecipazione diverso per ogni conferenza.</span><span class="sxs-lookup"><span data-stu-id="14e20-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="14e20-124">**Ammetti utenti anonimi per impostazione predefinita** Selezionare questa casella di controllo se gli utenti anonimi (ovvero non autenticati) sono autorizzati a partecipare alle conferenze per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="14e20-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="14e20-125">Deselezionare la casella di controllo se, per impostazione predefinita, agli utenti anonimi non è consentito partecipare alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="14e20-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="14e20-126">**URL logo** Digitare l'URL con l'immagine da utilizzare per gli inviti a conferenze personalizzati.</span><span class="sxs-lookup"><span data-stu-id="14e20-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="14e20-127">**URL guida** Digitare l'URL di un sito Web in cui gli utenti possono ottenere assistenza per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="14e20-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="14e20-128">**URL testo legale** Digitare l'URL di un sito Web con le informazioni legali e le dichiarazioni di non responsabilità per la conferenza.</span><span class="sxs-lookup"><span data-stu-id="14e20-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="14e20-129">**Testo piè di pagina personalizzato** Digitare il testo da utilizzare per gli inviti a conferenze personalizzati.</span><span class="sxs-lookup"><span data-stu-id="14e20-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="14e20-130">Per informazioni dettagliate sull'utilizzo di configurazioni riunioni, vedere [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="14e20-130">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) in the Operations documentation.</span></span> <span data-ttu-id="14e20-131">Per informazioni dettagliate sull'impostazione delle configurazioni per riunioni di grandi dimensioni, vedere [Setting Up Support for Large Meetings](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="14e20-131">For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) in the Planning documentation.</span></span>