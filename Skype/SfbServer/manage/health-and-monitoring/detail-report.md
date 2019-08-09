---
title: Report Dettagli conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Riepilogo: informazioni sul report Dettagli conferenza usato in Skype for Business Server.'
ms.openlocfilehash: 17337624c955dfa174f7b98772fdd836e82891d0
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/09/2019
ms.locfileid: "36271397"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="ba3db-103">Report Dettagli conferenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ba3db-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="ba3db-104">**Riepilogo:** Informazioni sul report Dettagli conferenza usato in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ba3db-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="ba3db-105">Il report Dettagli conferenza offre informazioni dettagliate su tutti gli utenti che hanno partecipato a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-105">The Conference Detail Report provides detailed information about all the users who participated in a conference.</span></span> <span data-ttu-id="ba3db-106">Ad esempio, puoi visualizzare informazioni come la data e l'ora in cui un utente ha partecipato alla conferenza, la data e l'ora in cui l'utente ha lasciato la conferenza e l'agente utente dell'endpoint usato per connettere l'utente alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-106">For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference.</span></span> <span data-ttu-id="ba3db-107">È anche possibile visualizzare le informazioni sul ruolo dell'utente in ogni conferenza, ad esempio relatore o partecipante.</span><span class="sxs-lookup"><span data-stu-id="ba3db-107">You can also see information the user's role in each conference (for example, Presenter or Attendee).</span></span> <span data-ttu-id="ba3db-108">Forse la cosa più importante è vedere rapidamente gli utenti che partecipano e completano la conferenza e che gli utenti non sono stati in grado di partecipare e completare la conferenza con successo.</span><span class="sxs-lookup"><span data-stu-id="ba3db-108">Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="ba3db-109">Accesso al report Dettagli conferenza</span><span class="sxs-lookup"><span data-stu-id="ba3db-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="ba3db-110">È possibile accedere al report Dettagli conferenza dai report seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba3db-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="ba3db-111">[Report di controllo ammissione chiamata](call-admission-control-report.md) (facendo clic sulla metrica di dettaglio per una conferenza)</span><span class="sxs-lookup"><span data-stu-id="ba3db-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="ba3db-112">[Report elenco errori](failure-list-report.md) (facendo clic sulla metrica conferenza)</span><span class="sxs-lookup"><span data-stu-id="ba3db-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="ba3db-113">[Report attività utente](call-diagnostic-reports-per-user.md) (facendo clic sulla metrica URI conferenza)</span><span class="sxs-lookup"><span data-stu-id="ba3db-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="ba3db-114">Dal report Dettagli conferenza è possibile accedere al [report di diagnostica](diagnostic-report.md) facendo clic sulla metrica rapporto di diagnostica (dettaglio).</span><span class="sxs-lookup"><span data-stu-id="ba3db-114">From the Conference Detail Report you can access the [Diagnostic Report](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="ba3db-115">Filtri</span><span class="sxs-lookup"><span data-stu-id="ba3db-115">Filters</span></span>

<span data-ttu-id="ba3db-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ba3db-116">None.</span></span> <span data-ttu-id="ba3db-117">Non è possibile filtrare il report Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-117">You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="ba3db-118">Metriche</span><span class="sxs-lookup"><span data-stu-id="ba3db-118">Metrics</span></span>

<span data-ttu-id="ba3db-119">Nella tabella seguente sono elencate le informazioni fornite nella sezione informazioni conferenza del report Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="ba3db-120">**Metriche delle informazioni sulla conferenza**</span><span class="sxs-lookup"><span data-stu-id="ba3db-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="ba3db-121">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ba3db-121">**Name**</span></span>                 | <span data-ttu-id="ba3db-122">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ba3db-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ba3db-123">**URI conferenza**</span><span class="sxs-lookup"><span data-stu-id="ba3db-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="ba3db-124">URI assegnato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-124">URI assigned to the conference.</span></span> <span data-ttu-id="ba3db-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ba3db-125">For example:</span></span>  <br/> <span data-ttu-id="ba3db-126">SIP: kmyer@litwareinc.com; GRUU; opaque = app: conf: stato attiva: ID: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="ba3db-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="ba3db-127">**FQDN del pool**</span><span class="sxs-lookup"><span data-stu-id="ba3db-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="ba3db-128">Nome di dominio completo del pool di registrazione o del server perimetrale coinvolto in una sessione.</span><span class="sxs-lookup"><span data-stu-id="ba3db-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="ba3db-129">**Ora di inizio**</span><span class="sxs-lookup"><span data-stu-id="ba3db-129">**Start time**</span></span> <br/>     | <span data-ttu-id="ba3db-130">Data e ora in cui è stata avviata la conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="ba3db-131">**Organizzatore**</span><span class="sxs-lookup"><span data-stu-id="ba3db-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="ba3db-132">Indirizzo SIP dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="ba3db-133">**Ora di fine**</span><span class="sxs-lookup"><span data-stu-id="ba3db-133">**End time**</span></span> <br/>       | <span data-ttu-id="ba3db-134">Data e ora di fine della conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="ba3db-135">Nella tabella seguente sono elencate le informazioni fornite nella sezione partecipazione alla conferenza del report Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="ba3db-136">**Metriche per la partecipazione alla conferenza**</span><span class="sxs-lookup"><span data-stu-id="ba3db-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="ba3db-137">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ba3db-137">**Name**</span></span>|<span data-ttu-id="ba3db-138">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ba3db-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ba3db-139">**Utente**</span><span class="sxs-lookup"><span data-stu-id="ba3db-139">**User**</span></span> <br/> |<span data-ttu-id="ba3db-140">Indirizzo SIP dell'utente che ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="ba3db-141">**Ruolo**</span><span class="sxs-lookup"><span data-stu-id="ba3db-141">**Role**</span></span> <br/> |<span data-ttu-id="ba3db-142">Ruolo (ad esempio, relatore) riprodotto dal partecipante alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="ba3db-143">**Connettività**</span><span class="sxs-lookup"><span data-stu-id="ba3db-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="ba3db-144">Connettività di rete (in genere da interno o da esterno) per il partecipante.</span><span class="sxs-lookup"><span data-stu-id="ba3db-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="ba3db-145">**Tempo di partecipazione**</span><span class="sxs-lookup"><span data-stu-id="ba3db-145">**Join time**</span></span> <br/> |<span data-ttu-id="ba3db-146">Data e ora in cui il partecipante ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="ba3db-147">**Ora di uscita**</span><span class="sxs-lookup"><span data-stu-id="ba3db-147">**Leave time**</span></span> <br/> |<span data-ttu-id="ba3db-148">Data e ora in cui il partecipante ha lasciato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="ba3db-149">**Agente utente**</span><span class="sxs-lookup"><span data-stu-id="ba3db-149">**User agent**</span></span> <br/> |<span data-ttu-id="ba3db-150">Identificatore per il software usato dall'endpoint del partecipante.</span><span class="sxs-lookup"><span data-stu-id="ba3db-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="ba3db-151">**Report di diagnostica**</span><span class="sxs-lookup"><span data-stu-id="ba3db-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="ba3db-152">Fornisce informazioni di diagnostica e risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="ba3db-152">Provides diagnostic and troubleshooting information.</span></span> <span data-ttu-id="ba3db-153">Inclusi i codici di risposta SIP, le intestazioni di diagnostica, le ore di conferenza e gli ID di diagnostica per le sessioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="ba3db-153">Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="ba3db-154">Nella tabella seguente sono elencate le informazioni fornite nella sezione modalità conferenza del report Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="ba3db-155">**Metriche delle modalità conferenza**</span><span class="sxs-lookup"><span data-stu-id="ba3db-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="ba3db-156">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ba3db-156">**Name**</span></span>|<span data-ttu-id="ba3db-157">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ba3db-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ba3db-158">**Utente**</span><span class="sxs-lookup"><span data-stu-id="ba3db-158">**User**</span></span> <br/> |<span data-ttu-id="ba3db-159">Indirizzo SIP dell'utente che ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="ba3db-160">**Tempo di partecipazione**</span><span class="sxs-lookup"><span data-stu-id="ba3db-160">**Join time**</span></span> <br/> |<span data-ttu-id="ba3db-161">Data e ora in cui il partecipante ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="ba3db-162">**Ora di uscita**</span><span class="sxs-lookup"><span data-stu-id="ba3db-162">**Leave time**</span></span> <br/> |<span data-ttu-id="ba3db-163">Data e ora in cui un partecipante ha lasciato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="ba3db-164">**URI di conferenza server**</span><span class="sxs-lookup"><span data-stu-id="ba3db-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="ba3db-165">URI per il server delle conferenze usato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="ba3db-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="ba3db-166">**Report di diagnostica**</span><span class="sxs-lookup"><span data-stu-id="ba3db-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="ba3db-167">Fornisce informazioni di diagnostica e risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="ba3db-167">Provides diagnostic and troubleshooting information.</span></span> <span data-ttu-id="ba3db-168">Inclusi i codici di risposta SIP, le intestazioni di diagnostica, le ore di conferenza e gli ID di diagnostica per le sessioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="ba3db-168">Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


