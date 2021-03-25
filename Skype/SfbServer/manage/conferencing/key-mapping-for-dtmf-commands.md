---
title: Gestire il mapping dei tasti per i comandi DTMF in Skype for Business Server
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
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Riepilogo: informazioni su come gestire il mapping dei tasti dei comandi DTMF (Dual Tone Multi-Frequency) in Skype for Business Server.'
ms.openlocfilehash: 6b409ccce10128fdd7776e3ea77d6ee17d4a49f4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119445"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a><span data-ttu-id="01381-103">Gestire il mapping dei tasti per i comandi DTMF in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="01381-103">Manage key mapping for DTMF commands in Skype for Business Server</span></span>
 
<span data-ttu-id="01381-104">**Riepilogo:** Informazioni su come gestire il mapping dei tasti dei comandi DTMF (Dual Tone Multi-Frequency) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="01381-104">**Summary:** Learn how to manage key mapping of dual-tone multi-frequency (DTMF) commands in Skype for Business Server.</span></span>
  
<span data-ttu-id="01381-105">Gli utenti delle conferenze telefoniche con accesso esterno possono premere i tasti sulla tastiera del telefono per eseguire comandi DTMF (Dual-Tone Multi-Frequency).</span><span class="sxs-lookup"><span data-stu-id="01381-105">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="01381-106">I comandi DTMF consentono agli utenti che affollano una conferenza di controllare le impostazioni della conferenza (ad esempio, la disattivazione e l'attivazione dell'audio o il blocco e lo sblocco della conferenza) utilizzando la tastiera del telefono.</span><span class="sxs-lookup"><span data-stu-id="01381-106">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> 
  
<span data-ttu-id="01381-107">Per gestire le chiavi utilizzate per i comandi DTMF, utilizzare Skype for Business Server Management Shell con i cmdlet **Get-CsDialinConferencingDtmfConfiguration,** **Set-CsDialinConferencingDtmfConfiguration** e **New-CsDialinConferencingDtmfConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="01381-107">To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**, and **New-CsDialinConferencingDtmfConfiguration** cmdlets.</span></span>
  
<span data-ttu-id="01381-108">Quando si creano nuove impostazioni DTMF per i siti, le impostazioni del sito hanno la precedenza sulle impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="01381-108">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="01381-109">Gestire il mapping dei tasti dei comandi DTMF</span><span class="sxs-lookup"><span data-stu-id="01381-109">Manage the key mapping of DTMF commands</span></span>

1. <span data-ttu-id="01381-110">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="01381-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="01381-111">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="01381-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="01381-112">Per visualizzare le impostazioni DTMF utilizzate per le conferenze telefoniche con accesso esterno, al prompt dei comandi eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="01381-112">To view the DTMF settings used for dial-in conferencing, run the following command at the command prompt :</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. <span data-ttu-id="01381-113">Per modificare le impostazioni DTMF utilizzate per le conferenze telefoniche con accesso esterno, eseguire il cmdlet seguente e specificare il tasto da premere per ogni opzione che si desidera modificare:</span><span class="sxs-lookup"><span data-stu-id="01381-113">To modify the DTMF settings used for dial-in conferencing, run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. <span data-ttu-id="01381-114">(Facoltativo) Per creare set aggiuntivi di comandi DTMF per siti specifici, utilizzare il cmdlet **New-CsDialinConferencingDtmfConfiguration** con un'identità di sito.</span><span class="sxs-lookup"><span data-stu-id="01381-114">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span>
    
<span data-ttu-id="01381-115">Nell'esempio seguente viene scambiato il tasto premuto per abilitare o disabilitare gli annunci e il tasto premuto per disattivare e riattivare l'audio di tutti i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="01381-115">The following example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="01381-116">Poiché non viene specificata alcuna identità, queste modifiche si applicano alle impostazioni DTMF globali:</span><span class="sxs-lookup"><span data-stu-id="01381-116">Because no Identity is specified, these changes apply to the global DTMF settings:</span></span>
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

<span data-ttu-id="01381-117">Per ulteriori informazioni, vedere [Get-CsDialInConferencingDtmfConfiguration,](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)e [New-CsDialInConferencingDtmfConfiguration.](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="01381-117">For more information, see [Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps), and [New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span></span>
