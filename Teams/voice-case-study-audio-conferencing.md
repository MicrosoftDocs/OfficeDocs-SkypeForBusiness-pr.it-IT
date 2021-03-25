---
title: Case study di Teams voice Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Case study vocale di Teams per multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: 085c9994bc2522d1ab56abc1670113e22d35f642
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121304"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="29557-103">Case study di Contoso: Audioconferenze</span><span class="sxs-lookup"><span data-stu-id="29557-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="29557-104">Per comprendere cosa sono le audioconferenze, i costi, la disponibilità e il suo funzionamento, Contoso ha esaminato &mdash; &mdash; le [audioconferenze in Office 365.](deploy-audio-conferencing-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="29557-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="29557-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="29557-105">Overview</span></span> 

<span data-ttu-id="29557-106">Per le audioconferenze, Contoso ha usato numeri di telefono ben noti all'interno dell'organizzazione, oltre che esternamente.</span><span class="sxs-lookup"><span data-stu-id="29557-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="29557-107">Poiché Contoso voleva mantenere questi numeri dove possibile, ha esaminato le informazioni sull'assegnazione di numeri di telefono dedicati e condivisi al bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="29557-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="29557-108">In base alle ricerche effettuate, Contoso ha preso le decisioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="29557-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="29557-109">Solo un segmento della popolazione che ospita regolarmente chiamate di audioconferenza riceverebbe licenze di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="29557-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="29557-110">Contoso userebbe numeri di telefono dedicati e porterebbe i numeri esistenti per l'uso con le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="29557-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="29557-111">Poiché gli utenti contoso usavano Skype for Business e le cassette postali di tutti gli utenti risiedono online, molti utenti hanno già in programma riunioni.</span><span class="sxs-lookup"><span data-stu-id="29557-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="29557-112">Contoso leggere [Usare il servizio](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) di migrazione delle riunioni per sapere che le riunioni esistenti vengono aggiornate automaticamente per Contoso quando l'utente finale cambia in modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="29557-112">Contoso read [Using the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="29557-113">Configurazione</span><span class="sxs-lookup"><span data-stu-id="29557-113">Configuration</span></span>

<span data-ttu-id="29557-114">I numeri di telefono associati alle audioconferenze vengono definiti numeri di servizio all'interno del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="29557-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="29557-115">Per le località che usano i Piani per chiamate, per convertire i numeri di telefono esistenti dal gestore telefonico a Office 365, Contoso ha seguito la procedura descritta in Ottenere i numeri di telefono [del servizio.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="29557-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="29557-116">Per assegnare la licenza di audioconferenza all'utente finale nel progetto pilota tecnico, l'amministratore contoso ha seguito la procedura descritta in Gestire le [impostazioni di audioconferenza per l'organizzazione.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="29557-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="29557-117">Per il progetto pilota e la migrazione aziendale, Contoso ha usato le licenze basate su gruppi seguendo la procedura descritta in Assegnare licenze agli utenti in base all'appartenenza ai gruppi [in Azure Active Directory.](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="29557-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

