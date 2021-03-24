---
title: Indicazioni per larghezza di banda ridotta per Microsoft Teams per l'istruzione
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Articolo su Microsoft Teams per l'istruzione per risolvere i problemi di video e riunioni associati a una ridotta larghezza di banda. Genitori, educatori o amministratori IT hanno a disposizione varie opzioni per migliorare l'esperienza con Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: b254bfb89a96efed65e2c1fdba1c345825d81dc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111082"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a><span data-ttu-id="89442-104">Indicazioni per le situazioni di larghezza di banda ridotta per Teams per l'istruzione</span><span class="sxs-lookup"><span data-stu-id="89442-104">Help for low bandwidth situations for Teams for EDU</span></span>

<span data-ttu-id="89442-105">Quando si lavora in Microsoft Teams, molti elementi di rete possono incidere sulle prestazioni e la larghezza di banda ridotta è uno dei fattori che possono sembrare totalmente al di fuori del proprio controllo.</span><span class="sxs-lookup"><span data-stu-id="89442-105">There are a lot of network elements when it comes to working with Microsoft Teams that can affect performance, and low bandwidth is one of the situations that can feel entirely out of your control.</span></span> <span data-ttu-id="89442-106">Tenere in considerazione gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="89442-106">Consider the following:</span></span>

- <span data-ttu-id="89442-107">Connessione Internet a bassa velocità per l'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="89442-107">A low-speed internet connection for the school.</span></span>
- <span data-ttu-id="89442-108">Connessione Internet a bassa velocità per uno o più studenti.</span><span class="sxs-lookup"><span data-stu-id="89442-108">A low-speed internet connection for one or more students.</span></span>
- <span data-ttu-id="89442-109">Orari in cui la larghezza di banda è ridotta a causa dell'utilizzo della rete in un'area.</span><span class="sxs-lookup"><span data-stu-id="89442-109">Times of the day when there is low bandwidth due to network usage in an area.</span></span>
- <span data-ttu-id="89442-110">Periodi in cui la larghezza di banda si riduce a causa di interruzioni locali non dell'istituto di istruzione o degli studenti, ma che comunque incidono sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="89442-110">Low bandwidth periods due to outages local to neither the school nor to students, but which impact performance nonetheless.</span></span>
- <span data-ttu-id="89442-111">Problemi che sono solo apparentemente associati alla larghezza di banda, ad esempio problemi hardware.</span><span class="sxs-lookup"><span data-stu-id="89442-111">Non-bandwidth issues (for example, issues with hardware) that masquerade as low bandwidth issues.</span></span>

<span data-ttu-id="89442-112">Questo articolo illustra le procedure consigliate da seguire per svariate attività di Teams quando si ha a che fare con un problema di larghezza di banda ridotta.</span><span class="sxs-lookup"><span data-stu-id="89442-112">This article will give you best practices to follow for a variety of Teams activities when you're faced with a low-bandwidth issue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89442-113">Leggere le informazioni su [Come viene usata la memoria in Microsoft Teams](teams-memory-usage-perf.md). Ai problemi di larghezza di banda ridotta potrebbero infatti accompagnarsi problemi di risorse nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="89442-113">There's information here on [How Microsoft Teams uses memory](teams-memory-usage-perf.md), because in addition to low bandwidth problems, you may be having resource issues on your device.</span></span> <span data-ttu-id="89442-114">Se si cercano indicazioni sulla rete per Microsoft Teams, vedere [Preparare la rete dell'organizzazione per Microsoft Teams](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="89442-114">If you're looking for network guidance for Microsoft Teams, review [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a><span data-ttu-id="89442-115">Risoluzione dei problemi di larghezza di banda ridotta per amministratori IT</span><span class="sxs-lookup"><span data-stu-id="89442-115">Resolving low bandwidth issues for ITAdmins</span></span>

<span data-ttu-id="89442-116">Per gli amministratori IT, l'aspetto più importante da ricordare è che, sebbene esistano soluzioni rapide ai problemi di larghezza di banda estesi, è consigliabile valutare i casi con attenzione, perché alcuni problemi possono essere risolti a livello di singolo docente o anche di singolo studente o genitore.</span><span class="sxs-lookup"><span data-stu-id="89442-116">The important thing to remember, as an ITAdmin, is that while you have solutions for low bandwidth issues that are wide-spread that will resolve problems quickly, this should be considered carefully, as some issues may be able to resolved with a more narrow focus taken at the educator or even the student/parent level.</span></span>

<span data-ttu-id="89442-117">In breve, agire come amministratore IT ha senso se i problemi di larghezza di banda riguardano un ampio gruppo di studenti e anche se le azioni intraprese a livello di studente o docente non sono state utili.</span><span class="sxs-lookup"><span data-stu-id="89442-117">In short, if the low bandwidth issue occurs for a wide group of students, taking action as an ITAdmin makes sense, and it also makes sense if the actions taken at the student/educator level haven't been helpful.</span></span>

> [!NOTE]
> <span data-ttu-id="89442-118">Se si ha tempo da investire, la [Guida sul controllo della qualità dell'esperienza](quality-of-experience-review-guide.md) è una lettura utile, che non è specifica per il settore dell'istruzione, ma offre comunque informazioni preziose.</span><span class="sxs-lookup"><span data-stu-id="89442-118">If you've got the time to invest, the [Quality of Experience Review Guide](quality-of-experience-review-guide.md) is a worthwhile read (this is not EDU-specific, but it will still have valuable information).</span></span> <span data-ttu-id="89442-119">Questo permetterà agli amministratori IT esperti di analizzare a fondo l'esperienza dei propri insegnanti e studenti.</span><span class="sxs-lookup"><span data-stu-id="89442-119">This will allow experienced ITAdmins to go in-depth on the experience for their educators and students.</span></span>

### <a name="meetings-and-video"></a><span data-ttu-id="89442-120">Riunioni e video</span><span class="sxs-lookup"><span data-stu-id="89442-120">Meetings and video</span></span>

<span data-ttu-id="89442-121">Una delle aree di attenzione principali per quanto riguarda i problemi di larghezza di banda sono le riunioni e in particolare il video nelle riunioni.</span><span class="sxs-lookup"><span data-stu-id="89442-121">A primary focus for low bandwidth issues are meetings, and specifically video in meetings.</span></span> <span data-ttu-id="89442-122">Di seguito sono riportate alcune azioni che un amministratore IT può considerare per gestire i problemi segnalati da studenti o docenti e migliorare l'esperienza di riunione in un ambiente didattico.</span><span class="sxs-lookup"><span data-stu-id="89442-122">We have some of the actions below that an ITAdmin should consider when dealing with issues reported by students or educators in regard to having the best meeting experience in an educational setting.</span></span>

#### <a name="meeting-policies"></a><span data-ttu-id="89442-123">Criteri di riunione</span><span class="sxs-lookup"><span data-stu-id="89442-123">Meeting policies</span></span>

<span data-ttu-id="89442-124">Per quanto riguarda le riunioni, l'area in cui si concentrano i problemi dovuti a larghezza di banda insufficiente è quella del video.</span><span class="sxs-lookup"><span data-stu-id="89442-124">In regards to meetings, one of the most concerning areas for low bandwidth situations has to do with videos.</span></span> <span data-ttu-id="89442-125">Fortunatamente, Teams si adatta automaticamente alla larghezza di banda rilevata e l'amministratore IT può anche impostare opzioni dei criteri a livello di organizzatore e/o di utente, mirate a offrire a tutti la migliore esperienza possibile in base alla larghezza di banda disponibile in un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="89442-125">Fortunately, in addition to Teams being able to scale to detected bandwidth automatically, you as an ITAdmin have policy options you can set at the per-organizer and/or per-user level to give everyone the best experience in light of the bandwidth they have to work with at a given time.</span></span>

<span data-ttu-id="89442-126">Alcuni degli elementi che è possibile impostare tramite criteri includono:</span><span class="sxs-lookup"><span data-stu-id="89442-126">Some of the things you can set via policy include:</span></span>

- <span data-ttu-id="89442-127">Disabilitazione completa del video, in modo che nessuno possa abilitarlo.</span><span class="sxs-lookup"><span data-stu-id="89442-127">Disabling video altogether, so no one could enable it.</span></span>
- <span data-ttu-id="89442-128">Velocità in bit dei contenuti multimediali (si imposta a livello di utente).</span><span class="sxs-lookup"><span data-stu-id="89442-128">Media bit rate (this is set per-user).</span></span>

<span data-ttu-id="89442-129">Per altre informazioni sulle opzioni disponibili e per informazioni dettagliate sui criteri che può essere necessario impostare per le riunioni e il video, vedere [Impostazioni dei criteri per le riunioni in Teams: audio e video](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video).</span><span class="sxs-lookup"><span data-stu-id="89442-129">To learn more about your options, and to walk through the specifics of what policies you'd need to set for meetings and video, check out [Meeting policy settings in Teams: Audio and video](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video) for detailed walk-through information.</span></span>

#### <a name="screen-sharing-policies"></a><span data-ttu-id="89442-130">Criteri di condivisione dello schermo</span><span class="sxs-lookup"><span data-stu-id="89442-130">Screen sharing policies</span></span>

<span data-ttu-id="89442-131">In altri casi, è possibile che i docenti stiano condividendo l'intero schermo con gli studenti, mentre la condivisione deve essere limitata a un'applicazione rilevante per la lezione in corso.</span><span class="sxs-lookup"><span data-stu-id="89442-131">In other cases, educators may be sharing their entire screen to students, when sharing should be limited to an application relevant to the lesson being taught.</span></span> <span data-ttu-id="89442-132">Questo può essere impostato anche tramite criteri, se è un metodo preferibile rispetto a lasciare la scelta ai singoli docenti.</span><span class="sxs-lookup"><span data-stu-id="89442-132">This can also be set via policy, if that's a more desirable way to do it than to have educators making that choice individually.</span></span>

<span data-ttu-id="89442-133">Per informazioni sul modo in cui è possibile limitare la condivisione dello schermo con le impostazioni dei criteri, vedere [Impostazioni dei criteri per le riunioni in Teams: condivisione dello schermo](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video).</span><span class="sxs-lookup"><span data-stu-id="89442-133">For a good idea of what you can do about limiting screen sharing via policy settings, check out [Meeting policy settings in Teams: Screen sharing](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video).</span></span>

#### <a name="dial-in-number-for-meetings"></a><span data-ttu-id="89442-134">Numero telefonico di accesso esterno per le riunioni</span><span class="sxs-lookup"><span data-stu-id="89442-134">Dial-in number for meetings</span></span>

<span data-ttu-id="89442-135">Per alcuni studenti potrebbe essere più facile accedere ad alcune sessioni della classe tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="89442-135">It may be easier for some students to attempt to dial in to some classroom sessions.</span></span> <span data-ttu-id="89442-136">È possibile fornire un numero di accesso esterno per le riunioni di Teams, in modo che gli studenti che riscontrano problemi possano telefonare in alternativa alla partecipazione a una riunione video.</span><span class="sxs-lookup"><span data-stu-id="89442-136">You can provide a dial-in number for Teams meetings, so students with issues can phone in as an alternative to attending a video meeting.</span></span>

<span data-ttu-id="89442-137">Per altre informazioni, vedere [Impostare i numeri di telefono inclusi negli inviti in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="89442-137">For more information on this, you can read [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="low-bandwidth-scenarios-as-an-educator"></a><span data-ttu-id="89442-138">Scenari di larghezza di banda ridotta come docenti</span><span class="sxs-lookup"><span data-stu-id="89442-138">Low bandwidth scenarios as an educator</span></span>

<span data-ttu-id="89442-139">I docenti dovrebbero sentirsi autorizzati a intraprendere le azioni necessarie per risolvere i problemi di larghezza di banda. L'intervento dei docenti può essere una scelta migliore rispetto a quello dell'amministratore IT nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="89442-139">Educators should feel empowered to take steps to resolve low bandwidth issues, and may be a superior choice to ITAdmin action in the following situations:</span></span>

- <span data-ttu-id="89442-140">Se il problema è intermittente o relativamente transitorio.</span><span class="sxs-lookup"><span data-stu-id="89442-140">If the problem is intermittent, or relatively transitory.</span></span>
- <span data-ttu-id="89442-141">Se c'è un orario specifico in cui si può ipotizzare che si verifichino problemi o se il periodo di tempo in cui la larghezza di banda è ridotta ha una certa prevedibilità.</span><span class="sxs-lookup"><span data-stu-id="89442-141">If there is a specific time of the day you can anticipate there being an issue, or the low bandwidth period has some predictability to it.</span></span>

<span data-ttu-id="89442-142">In questi casi, si possono compiere alcune azioni.</span><span class="sxs-lookup"><span data-stu-id="89442-142">In these situations, you can take some actions.</span></span>

<span data-ttu-id="89442-143">Per altre informazioni, vedere come [Usare Teams per la didattica quando la larghezza di banda è ridotta](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span><span class="sxs-lookup"><span data-stu-id="89442-143">For more information, check out [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span></span>

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a><span data-ttu-id="89442-144">Scenari di larghezza di banda ridotta come genitori o studenti</span><span class="sxs-lookup"><span data-stu-id="89442-144">Low bandwidth scenarios as a parent or student</span></span>

<span data-ttu-id="89442-145">Ci sono anche situazioni, di cui è necessario discutere in modo proattivo con i docenti, in cui il problema della larghezza di banda può essere sul versante dello studente. Ad esempio, un numero elevato di studenti riesce a guardare le lezioni video senza problemi, mentre un numero limitato di studenti ha difficoltà.</span><span class="sxs-lookup"><span data-stu-id="89442-145">There are also situations, and you should proactively discuss them with your educators, where the bandwidth problem may be on the student's side (for example, a large number of students are able to watch the video lessons without issue, but a small number of students have difficulties).</span></span>

<span data-ttu-id="89442-146">Non è ragionevole aspettarsi che tutti i genitori siano in grado di risolvere questi problemi, inoltre i problemi di larghezza di banda ridotta possono essere al di fuori del controllo di uno studente o di un genitore. L'abitazione potrebbe non avere accesso alla banda larga, possono esserci molte persone nell'area immediatamente limitrofa che consumano larghezza di banda, potrebbe esserci instabilità della rete Internet e così via.</span><span class="sxs-lookup"><span data-stu-id="89442-146">It's not reasonable to expect many parents to be able to troubleshoot these issues, and low bandwidth issues may be out of a student or parent's control (their home may not have access to high bandwidth, they may have a lot of people in their immediate area consuming bandwidth and affecting what they can do, there may be internet instability, and so on).</span></span>

<span data-ttu-id="89442-147">L'articolo [Usare Teams per la didattica quando la larghezza di banda è ridotta](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) raccoglie consigli utili per genitori e studenti, in caso di problemi.</span><span class="sxs-lookup"><span data-stu-id="89442-147">We've put together guidance in our [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) article for parents and students as well, you can review and try these recommendations if you're having any problems.</span></span>