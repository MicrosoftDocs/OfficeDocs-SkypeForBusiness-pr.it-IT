---
title: Configurazione della riunione creare nuovi o modifica esistenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: Le impostazioni di configurazione della riunione definiscono l'esperienza di partecipazione dell'utente per le conferenze pianificate dagli utenti. Queste impostazioni si applicano solo alle riunioni pianificate. Non si applicano invece alle riunioni ad hoc create facendo clic sull'opzione Riunione immediata nel client.
ms.openlocfilehash: ce94eff347d4cbae35d78ced44873e8164abe0d5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691401"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="29674-105">Configurazione riunione: crearne una nuova o modificarne una esistente</span><span class="sxs-lookup"><span data-stu-id="29674-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="29674-p102">Le impostazioni di configurazione delle riunioni definiscono l'esperienza di partecipazione degli utenti alle conferenze pianificate. Queste impostazioni riguardano solo le riunioni pianificate e non quelle ad hoc create facendo clic sull'opzione **Riunione immediata** nel client.</span><span class="sxs-lookup"><span data-stu-id="29674-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="29674-109">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="29674-109">UI Reference</span></span>

<span data-ttu-id="29674-110">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="29674-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="29674-111">**Ambito** Identifica l'ambito della configurazione della riunione che si sta creando o modificando: globale, sito o pool.</span><span class="sxs-lookup"><span data-stu-id="29674-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="29674-112">**Nome** Le configurazioni delle riunioni sono denominate per impostazione predefinita e il nome non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="29674-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="29674-113">**Ingresso di bypass per i chiamanti PSTN** Selezionare questa casella di controllo per ammettere automaticamente gli utenti che effettuano la chiamata alla conferenza tramite una linea telefonica pubblica con Switched Telephone Network (PSTN).</span><span class="sxs-lookup"><span data-stu-id="29674-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="29674-114">Deselezionare la casella di controllo per instradare i chiamanti PSTN alla sala di attesa della conferenza, dove rimangono in attesa fino a quando un relatore non concede loro l'accesso alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="29674-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="29674-115">**Designa come relatore** Selezionare la categoria di utenti (oltre all'organizzatore della riunione) che vengono automaticamente designati come relatori quando partecipano a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="29674-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="29674-116">Indipendentemente da questa impostazione, i relatori possono essere designati in modo esplicito come tali quando viene pianificata la conferenza oppure possono essere promossi in modo esplicito a relatori durante la conferenza.</span><span class="sxs-lookup"><span data-stu-id="29674-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="29674-117">Le opzioni sono:</span><span class="sxs-lookup"><span data-stu-id="29674-117">The options are:</span></span>

  - <span data-ttu-id="29674-118">**Nessuno** Selezionare questa opzione se non si vuole che l'organizzatore venga indicato automaticamente come relatore.</span><span class="sxs-lookup"><span data-stu-id="29674-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="29674-119">**Società** Selezionare questa opzione per designare automaticamente solo i membri dell'organizzazione come relatori.</span><span class="sxs-lookup"><span data-stu-id="29674-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="29674-120">**Tutti gli utenti** Selezionare questa opzione per designare automaticamente tutti gli utenti come relatori.</span><span class="sxs-lookup"><span data-stu-id="29674-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="29674-121">**Tipo di conferenza assegnata per impostazione predefinita** Questa impostazione controlla se Outlook Conferencing AddIn Pianifica sempre le conferenze tramite la conferenza assegnata dell'organizzatore, in modo che le conferenze pianificate abbiano sempre lo stesso URL di join e informazioni audio.</span><span class="sxs-lookup"><span data-stu-id="29674-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="29674-122">Selezionare questa casella di controllo per fare in modo che le conferenze pianificate usino sempre lo stesso URL per la partecipazione.</span><span class="sxs-lookup"><span data-stu-id="29674-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="29674-123">Deselezionare la casella di controllo per usare un URL per la partecipazione diverso per ogni conferenza.</span><span class="sxs-lookup"><span data-stu-id="29674-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="29674-124">**Ammettere gli utenti anonimi per impostazione predefinita** Selezionare questa casella di controllo se gli utenti anonimi, ovvero non autenticati, sono autorizzati a partecipare alle conferenze per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="29674-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="29674-125">Deselezionare la casella di controllo se, per impostazione predefinita, agli utenti anonimi non è consentito partecipare alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="29674-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="29674-126">**URL del logo** Digitare l'URL che contiene l'immagine da usare per gli inviti alle conferenze personalizzate.</span><span class="sxs-lookup"><span data-stu-id="29674-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="29674-127">**URL della Guida** Digitare l'URL di un sito Web in cui gli utenti possono ottenere assistenza per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="29674-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="29674-128">**URL di testo legale** Digitare l'URL di un sito Web che contiene le informazioni legali e le dichiarazioni di non responsabilità per la conferenza.</span><span class="sxs-lookup"><span data-stu-id="29674-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="29674-129">**Testo del piè** di pagina personalizzato Digitare il testo da usare per gli inviti alle conferenze personalizzati.</span><span class="sxs-lookup"><span data-stu-id="29674-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="29674-p107">Per informazioni dettagliate sulle configurazioni delle riunioni, vedere [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) nella documentazione relativa alle operazioni. Per informazioni dettagliate sull'impostazione delle configurazioni per riunioni di grandi dimensioni, vedere [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="29674-p107">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation. For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


