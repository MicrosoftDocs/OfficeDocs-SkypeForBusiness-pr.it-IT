---
title: Verificare le impostazioni di configurazione del trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi. '
ms.openlocfilehash: bfb09511c8d074555c0b84d2da141a029f63a01a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992563"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="c1417-103">Verificare le impostazioni di configurazione del trunk SIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c1417-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="c1417-104">Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="c1417-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="c1417-105">Queste impostazioni eseguono operazioni come specifica:</span><span class="sxs-lookup"><span data-stu-id="c1417-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="c1417-106">Se il bypass multimediale deve essere abilitato nei trunk.</span><span class="sxs-lookup"><span data-stu-id="c1417-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="c1417-107">Condizioni in cui vengono inviati i pacchetti RTCP (Real-Time Transport Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="c1417-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="c1417-108">Indipendentemente dal fatto che sia necessaria o meno la crittografia SRTP (Real-Time Protocol) in ogni trunk.</span><span class="sxs-lookup"><span data-stu-id="c1417-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="c1417-109">Quando si installa Skype for Business Server, viene creata una raccolta globale di impostazioni di configurazione trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="c1417-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="c1417-110">Gli amministratori possono inoltre creare raccolte di impostazioni personalizzate nell'ambito del sito o nell'ambito del servizio (solo per il servizio gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="c1417-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="c1417-111">Gli amministratori possono anche usare il cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) per verificare che un trunk sia in grado di convertire un numero come composto da un utente in un numero che può essere gestito dal gateway.</span><span class="sxs-lookup"><span data-stu-id="c1417-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="c1417-112">Le impostazioni di configurazione trunk possono essere testate solo usando Windows PowerShell e il cmdlet Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="c1417-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="c1417-113">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1417-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="c1417-114">**Per testare le impostazioni di configurazione del trunk SIP**</span><span class="sxs-lookup"><span data-stu-id="c1417-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="c1417-115">Questo comando verifica che le impostazioni di configurazione del trunk per il sito Redmond possano convertire correttamente il numero composto da 4255551212.</span><span class="sxs-lookup"><span data-stu-id="c1417-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
