---
title: Configurare le impostazioni di registrazione dettagli chiamata e qualità delle esperienze in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 'Riepilogo: informazioni su come configurare CDR e QoE in Skype for Business Server.'
ms.openlocfilehash: dd8611723e3d83f8a4553ba2148ee5ae29791e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802286"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="7629b-103">Configurare le impostazioni di registrazione dettagli chiamata e qualità delle esperienze in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7629b-103">Configure call detail recording and Quality of Experience settings in Skype for Business Server</span></span>
 
<span data-ttu-id="7629b-104">**Riepilogo:** Informazioni su come configurare CDR e QoE in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7629b-104">**Summary:** Learn how to configure CDR and QoE in Skype for Business Server.</span></span>
  
<span data-ttu-id="7629b-105">Configurare il monitoraggio CDR e QoE utilizzando i report di SQL Server Reporting Services per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7629b-105">Configure CDR and QoE monitoring using SQL Server Reporting Services reports for Skype for Business Server.</span></span>
  
## <a name="configure-cdr-and-qoe"></a><span data-ttu-id="7629b-106">Configurare CDR e QoE</span><span class="sxs-lookup"><span data-stu-id="7629b-106">Configure CDR and QoE</span></span>

<span data-ttu-id="7629b-107">Dopo aver associato un archivio di monitoraggio a un pool Front End, configurare l'archivio di monitoraggio e quindi aver installato e configurato SQL Server Reporting Services e Monitoring report è possibile gestire il monitoraggio di registrazione dettagli chiamata (CDR) e la qualità di esperienza (QoE) tramite Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7629b-107">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Skype for Business Server Management Shell.</span></span> <span data-ttu-id="7629b-108">I cmdlet di Skype for Business Server Management Shell consentono di abilitare e disabilitare il monitoraggio dei CDR e/o QoE per un sito specifico o per l'intera distribuzione di Skype for Business Server. che è possibile eseguire con un comando così semplice:</span><span class="sxs-lookup"><span data-stu-id="7629b-108">Skype for Business Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Skype for Business Server deployment; that can be done with a command as simple as this:</span></span>
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

<span data-ttu-id="7629b-109">Quando si installa Skype for Business Server, verrà installata anche una raccolta predefinita di impostazioni di configurazione globali per CDR e QoE.</span><span class="sxs-lookup"><span data-stu-id="7629b-109">When you install Skype for Business Server, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="7629b-110">I valori predefiniti di alcune delle impostazioni usate più di frequente da CDR sono mostrati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="7629b-110">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>
  
|<span data-ttu-id="7629b-111">**Proprietà**</span><span class="sxs-lookup"><span data-stu-id="7629b-111">**Property**</span></span>|<span data-ttu-id="7629b-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7629b-112">**Description**</span></span>|<span data-ttu-id="7629b-113">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="7629b-113">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7629b-114">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="7629b-114">EnableCDR</span></span>  <br/> |<span data-ttu-id="7629b-p103">Indica se la registrazione dettagli chiamata è abilitata o meno. Se è impostata su True, tutti i record CDR verranno raccolti e scritti nel database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="7629b-p103">Indicates whether or not CDR is enabled. If True, all CDR records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="7629b-117">Vero</span><span class="sxs-lookup"><span data-stu-id="7629b-117">True</span></span>  <br/> |
|<span data-ttu-id="7629b-118">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="7629b-118">EnablePurging</span></span>  <br/> |<span data-ttu-id="7629b-p104">Indica se i record CDR verranno eliminati periodicamente dal database. Se è impostata su True, i record verranno eliminati dopo il periodo di tempo specificato dalle proprietà KeepCallDetailForDays (per record CDR) e KeepErrorReportForDays (per errori CDR). Se False, i record verranno mantenuti indefinitamente.</span><span class="sxs-lookup"><span data-stu-id="7629b-p104">Indicates whether or not CDR records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors). If False, CDR records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="7629b-122">Vero</span><span class="sxs-lookup"><span data-stu-id="7629b-122">True</span></span>  <br/> |
|<span data-ttu-id="7629b-123">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="7629b-123">KeepCallDetailForDays</span></span>  <br/> |<span data-ttu-id="7629b-p105">Indica il numero di giorni per cui i record CDR verranno mantenuti nel database. Qualsiasi record che ha superato il numero di giorni specificato verrà eliminato automaticamente, ma solo se l'eliminazione è stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="7629b-p105">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="7629b-126">KeepCallDetailForDays può essere impostato su qualsiasi valore intero compreso tra 1 e 2562 giorni (circa 7 anni).</span><span class="sxs-lookup"><span data-stu-id="7629b-126">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span>  <br/> |<span data-ttu-id="7629b-127">60 giorni</span><span class="sxs-lookup"><span data-stu-id="7629b-127">60 days</span></span>  <br/> |
|<span data-ttu-id="7629b-128">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="7629b-128">KeepErrorReportForDays</span></span>  <br/> |<span data-ttu-id="7629b-129">Indica il numero di giorni in cui vengono mantenuti i report di errore di registrazione dettagli chiamata. gli eventuali rapporti precedenti al numero di giorni specificato verranno eliminati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7629b-129">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="7629b-130">I report di errore CDR sono rapporti di diagnostica caricati da applicazioni client come Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7629b-130">CDR error reports are diagnostic reports uploaded by client applications such as Skype for Business Server.</span></span>  <br/> <span data-ttu-id="7629b-131">È possibile impostare questa proprietà su qualsiasi valore intero compreso tra 1 e 2562 giorni.</span><span class="sxs-lookup"><span data-stu-id="7629b-131">You can set this property to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="7629b-132">60 giorni</span><span class="sxs-lookup"><span data-stu-id="7629b-132">60 days</span></span>  <br/> |
   
<span data-ttu-id="7629b-133">Analogamente, i valori predefiniti per le impostazioni QoE selezionate vengono mostrati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="7629b-133">Similarly, default values for selected QoE settings are shown in this table:</span></span>
  
|<span data-ttu-id="7629b-134">**Proprietà**</span><span class="sxs-lookup"><span data-stu-id="7629b-134">**Property**</span></span>|<span data-ttu-id="7629b-135">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7629b-135">**Description**</span></span>|<span data-ttu-id="7629b-136">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="7629b-136">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7629b-137">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="7629b-137">EnableQoE</span></span>  <br/> |<span data-ttu-id="7629b-p107">Indica se il monitoraggio QoE è abilitato. Se impostata su True, tutti i record QoE verranno raccolti e scritti nel database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="7629b-p107">Indicates whether or not QoE monitoring is enabled. If True, all QoE records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="7629b-140">Vero</span><span class="sxs-lookup"><span data-stu-id="7629b-140">True</span></span>  <br/> |
|<span data-ttu-id="7629b-141">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="7629b-141">EnablePurging</span></span>  <br/> |<span data-ttu-id="7629b-p108">Indica se i record QoE verranno eliminati periodicamente dal database. Se è impostata su True, i record verranno eliminati dopo il periodo di tempo specificato dalle proprietà KeepQoEDataForDays. Se False, i record QoE verranno mantenuti indefinitamente.</span><span class="sxs-lookup"><span data-stu-id="7629b-p108">Indicates whether or not QoE records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the KeepQoEDataForDays property. If False, QoE records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="7629b-145">Vero</span><span class="sxs-lookup"><span data-stu-id="7629b-145">True</span></span>  <br/> |
|<span data-ttu-id="7629b-146">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="7629b-146">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="7629b-p109">Indica il numero di giorni per cui i record QoE verranno mantenuti nel database. Qualsiasi record che ha superato il numero di giorni specificato verrà eliminato automaticamente, ma solo se l'eliminazione è stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="7629b-p109">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="7629b-149">KeepCallDetailForDays può essere impostato su qualsiasi valore intero compreso tra 1 e 2562 giorni.</span><span class="sxs-lookup"><span data-stu-id="7629b-149">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="7629b-150">60 giorni</span><span class="sxs-lookup"><span data-stu-id="7629b-150">60 days</span></span>  <br/> |
   
<span data-ttu-id="7629b-151">Se è necessario modificare queste impostazioni globali, è possibile utilizzare il Set-CsCdrConfiguration e i cmdlet Set-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="7629b-151">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets.</span></span> <span data-ttu-id="7629b-152">Ad esempio, questo comando (eseguito dall'interno di Skype for Business Server Management Shell) disattiva il monitoraggio CDR nell'ambito globale. a tale scopo, è possibile impostare la proprietà EnableCDR su false ($False):</span><span class="sxs-lookup"><span data-stu-id="7629b-152">For example, this command (run from within the Skype for Business Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

<span data-ttu-id="7629b-153">Si noti che la disabilitazione del monitoraggio non annulla l'associazione dell'archivio di monitoraggio dal pool Front End e non disinstallerà o influirà in alcun modo sul database di monitoraggio back-end.</span><span class="sxs-lookup"><span data-stu-id="7629b-153">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="7629b-154">Quando si utilizza Skype for Business Server Management Shell per disabilitare il monitoraggio di CDR o QoE, è possibile interrompere temporaneamente Skype for Business Server dalla raccolta e dall'archiviazione dei dati di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="7629b-154">When you use Skype for Business Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Skype for Business Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="7629b-155">Se, in questo caso, si desidera riprendere la raccolta e l'archiviazione di dati CDR, è sufficiente impostare di nuovo la proprietà EnableCDR su True ($True):</span><span class="sxs-lookup"><span data-stu-id="7629b-155">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

<span data-ttu-id="7629b-156">Analogamente, questo comando disabilita l'eliminazione dei record QoE a livello di ambito globale:</span><span class="sxs-lookup"><span data-stu-id="7629b-156">Similarly, this command disables the purging of QoE records at the global scope:</span></span>
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

<span data-ttu-id="7629b-p112">Oltre alle impostazioni globali, le impostazioni di configurazione di CDR e QoE possono essere assegnate all'ambito del sito. Ciò offre una maggiore flessibilità a livello di gestione per il monitoraggio. Ad esempio, un amministratore può abilitare il monitoraggio CDR per il sito di Redmond ma disabilitarlo per il sito di Dublino. Per creare nuove impostazioni di configurazione CDR a livello di ambito di sito, utilizzare un comando simile a questo:</span><span class="sxs-lookup"><span data-stu-id="7629b-p112">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope. This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site. To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>
  
```powershell
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

<span data-ttu-id="7629b-p113">È necessario ricordare che le impostazioni configurate a livello di ambito di sito hanno priorità maggiore rispetto alle impostazioni configurate a livello di ambito globale. Ad esempio, si supponga che il monitoraggio CDR sia abilitato a livello di ambito globale, ma disabilitato a livello di ambito di sito (per il sito di Redmond). Le informazioni sulle registrazioni dettagli chiamata non verranno quindi archiviate per gli utenti del sito di Redmond, ma verranno archiviate per gli utenti di altri siti, ovvero utenti gestiti dalle impostazioni globali invece che dalle impostazioni de sito di Redmond.</span><span class="sxs-lookup"><span data-stu-id="7629b-p113">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope. For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site). That means that call detail recording information will not be archived for users in the Redmond site. However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>
  
<span data-ttu-id="7629b-164">Nuove impostazioni di configurazione QoE possono essere create a livello di ambito di sito utilizzando un comando simile a questo:</span><span class="sxs-lookup"><span data-stu-id="7629b-164">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>
  
```powershell
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

<span data-ttu-id="7629b-165">Per ulteriori informazioni, digitare i comandi seguenti dall'interno di Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="7629b-165">For more information, type the following commands from within the Skype for Business Server Management Shell:</span></span>
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
