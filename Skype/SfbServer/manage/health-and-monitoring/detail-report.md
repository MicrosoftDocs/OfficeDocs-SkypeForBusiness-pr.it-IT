---
title: Rapporto Dettagli conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Riepilogo: informazioni sul rapporto Dettagli conferenza utilizzato in Skype for Business Server.'
ms.openlocfilehash: 245691fcb304a872942be4d5a9aabe8183b4db14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816906"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="dd36f-103">Rapporto Dettagli conferenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd36f-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="dd36f-104">**Riepilogo:** Informazioni sul rapporto Dettagli conferenza utilizzato in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dd36f-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="dd36f-p101">Il Rapporto Dettagli conferenza offre informazioni dettagliate su tutti gli utenti che hanno partecipato a una conferenza. È ad esempio possibile conoscere la data e l'ora in cui un utente si è unito alla conferenza o in cui l'ha abbandonata e l'agente utente dell'endpoint utilizzato per connettere tale utente alla conferenza. È anche possibile visualizzare informazioni sul ruolo dell'utente in ciascuna conferenza (relatore o partecipante). E ancora più importante, è possibile sapere rapidamente quali utenti si sono uniti alla conferenza e l'hanno completata e quali non ci sono riusciti.</span><span class="sxs-lookup"><span data-stu-id="dd36f-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="dd36f-109">Accesso al Rapporto Dettagli conferenza</span><span class="sxs-lookup"><span data-stu-id="dd36f-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="dd36f-110">Il Rapporto Dettagli conferenza è accessibile dai rapporti seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd36f-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="dd36f-111">[Call Admission Control Report](call-admission-control-report.md) (facendo clic sulla metrica Dettaglio per una conferenza)</span><span class="sxs-lookup"><span data-stu-id="dd36f-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="dd36f-112">[Failure List Report](failure-list-report.md) (facendo clic sulla metrica Conferenza)</span><span class="sxs-lookup"><span data-stu-id="dd36f-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="dd36f-113">[User Activity Report](call-diagnostic-reports-per-user.md) (facendo clic sulla metrica URI conferenza)</span><span class="sxs-lookup"><span data-stu-id="dd36f-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="dd36f-114">Dal Rapporto Dettagli conferenza è possibile accedere al [Diagnostic Report](diagnostic-report.md) facendo clic sulla metrica Rapporto di diagnostica (Dettaglio).</span><span class="sxs-lookup"><span data-stu-id="dd36f-114">From the Conference Detail Report you can access the [Diagnostic Report](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="dd36f-115">Filtri</span><span class="sxs-lookup"><span data-stu-id="dd36f-115">Filters</span></span>

<span data-ttu-id="dd36f-p102">Nessuno. Non è possibile applicare filtri al Rapporto Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="dd36f-p102">None. You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="dd36f-118">Metriche</span><span class="sxs-lookup"><span data-stu-id="dd36f-118">Metrics</span></span>

<span data-ttu-id="dd36f-119">La tabella seguente elenca le informazioni contenute nella sezione Informazioni conferenza del Rapporto Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="dd36f-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="dd36f-120">**Metriche Informazioni conferenza**</span><span class="sxs-lookup"><span data-stu-id="dd36f-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="dd36f-121">**Nome**</span><span class="sxs-lookup"><span data-stu-id="dd36f-121">**Name**</span></span>                 | <span data-ttu-id="dd36f-122">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="dd36f-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="dd36f-123">**URI conferenza**</span><span class="sxs-lookup"><span data-stu-id="dd36f-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="dd36f-p103">URI assegnato alla conferenza, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="dd36f-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="dd36f-126">SIP: kmyer@litwareinc. com; GRUU; opaque = app: conf: Focus: ID: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="dd36f-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="dd36f-127">**FQDN pool**</span><span class="sxs-lookup"><span data-stu-id="dd36f-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="dd36f-128">Nome di dominio completo del pool di registrazione o del server perimetrale operativo in una sessione.</span><span class="sxs-lookup"><span data-stu-id="dd36f-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="dd36f-129">**Ora di inizio**</span><span class="sxs-lookup"><span data-stu-id="dd36f-129">**Start time**</span></span> <br/>     | <span data-ttu-id="dd36f-130">Data e ora di inizio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="dd36f-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="dd36f-131">**Organizzatore**</span><span class="sxs-lookup"><span data-stu-id="dd36f-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="dd36f-132">Indirizzo SIP dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="dd36f-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="dd36f-133">**Ora di fine**</span><span class="sxs-lookup"><span data-stu-id="dd36f-133">**End time**</span></span> <br/>       | <span data-ttu-id="dd36f-134">Data e ora di fine della conferenza.</span><span class="sxs-lookup"><span data-stu-id="dd36f-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="dd36f-135">La tabella seguente elenca le informazioni fornite nella sezione Partecipazione conferenza del Rapporto Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="dd36f-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="dd36f-136">**Metriche di Partecipazione conferenza**</span><span class="sxs-lookup"><span data-stu-id="dd36f-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="dd36f-137">**Nome**</span><span class="sxs-lookup"><span data-stu-id="dd36f-137">**Name**</span></span>|<span data-ttu-id="dd36f-138">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="dd36f-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dd36f-139">**Utente**</span><span class="sxs-lookup"><span data-stu-id="dd36f-139">**User**</span></span> <br/> |<span data-ttu-id="dd36f-140">Indirizzo SIP dell'utente che ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="dd36f-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="dd36f-141">**Ruolo**</span><span class="sxs-lookup"><span data-stu-id="dd36f-141">**Role**</span></span> <br/> |<span data-ttu-id="dd36f-142">Ruolo, ad esempio Relatore, ricoperto dal partecipante alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="dd36f-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="dd36f-143">**Connettività**</span><span class="sxs-lookup"><span data-stu-id="dd36f-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="dd36f-144">Connettività di rete, solitamente Dall'interno o Dall'esterno, per il partecipante.</span><span class="sxs-lookup"><span data-stu-id="dd36f-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="dd36f-145">**Ora partecipazione**</span><span class="sxs-lookup"><span data-stu-id="dd36f-145">**Join time**</span></span> <br/> |<span data-ttu-id="dd36f-146">Data e ora in cui il partecipante si è unito alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="dd36f-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="dd36f-147">**Ora uscita**</span><span class="sxs-lookup"><span data-stu-id="dd36f-147">**Leave time**</span></span> <br/> |<span data-ttu-id="dd36f-148">Data e ora in cui il partecipante è uscito dalla conferenza.</span><span class="sxs-lookup"><span data-stu-id="dd36f-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="dd36f-149">**Agente utente**</span><span class="sxs-lookup"><span data-stu-id="dd36f-149">**User agent**</span></span> <br/> |<span data-ttu-id="dd36f-150">Identificatore del software utilizzato dall'endpoint del partecipante.</span><span class="sxs-lookup"><span data-stu-id="dd36f-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="dd36f-151">**Rapporti di diagnostica**</span><span class="sxs-lookup"><span data-stu-id="dd36f-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="dd36f-p104">Contiene informazioni relative alla diagnostica e alla risoluzione dei problemi, tra cui codici di risposta SIP, intestazioni di diagnostica, ore di partecipazione alla conferenza e ID diagnostica per le sessioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="dd36f-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="dd36f-154">Nella tabella seguente sono elencate le informazioni fornite nella sezione modalità conferenza del rapporto Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="dd36f-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="dd36f-155">**Metriche di Modalità conferenza**</span><span class="sxs-lookup"><span data-stu-id="dd36f-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="dd36f-156">**Nome**</span><span class="sxs-lookup"><span data-stu-id="dd36f-156">**Name**</span></span>|<span data-ttu-id="dd36f-157">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="dd36f-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dd36f-158">**Utente**</span><span class="sxs-lookup"><span data-stu-id="dd36f-158">**User**</span></span> <br/> |<span data-ttu-id="dd36f-159">Indirizzo SIP dell'utente che ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="dd36f-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="dd36f-160">**Ora partecipazione**</span><span class="sxs-lookup"><span data-stu-id="dd36f-160">**Join time**</span></span> <br/> |<span data-ttu-id="dd36f-161">Data e ora in cui il partecipante si è unito alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="dd36f-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="dd36f-162">**Ora uscita**</span><span class="sxs-lookup"><span data-stu-id="dd36f-162">**Leave time**</span></span> <br/> |<span data-ttu-id="dd36f-163">Data e ora in cui un partecipante è uscito dalla conferenza.</span><span class="sxs-lookup"><span data-stu-id="dd36f-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="dd36f-164">**URI server per conferenze**</span><span class="sxs-lookup"><span data-stu-id="dd36f-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="dd36f-165">URI per il server per conferenze utilizzato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="dd36f-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="dd36f-166">**Rapporti di diagnostica**</span><span class="sxs-lookup"><span data-stu-id="dd36f-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="dd36f-p105">Contiene informazioni relative alla diagnostica e alla risoluzione dei problemi, tra cui codici di risposta SIP, intestazioni di diagnostica, ore di partecipazione alla conferenza e ID diagnostica per le sessioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="dd36f-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


