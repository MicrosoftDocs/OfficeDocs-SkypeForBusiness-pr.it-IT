---
title: Criteri di conformità di accesso condizionale e Intune dispositivi supportati per Microsoft Teams Rooms
ms.author: czawideh
author: cazawideh
ms.reviewer: kspiess
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Informazioni sui criteri di accesso condizionale supportati e consigliati e Intune conformità dei dispositivi per Microsoft Teams Rooms.
ms.openlocfilehash: befe8faae5db204f5e15e307cadcc24f6867a487
ms.sourcegitcommit: 5fe5516f6118ce3fa0449ab194a6fe87bf48c664
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2022
ms.locfileid: "64732294"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms"></a>Criteri di conformità di accesso condizionale e Intune dispositivi supportati per Microsoft Teams Rooms

Questo articolo fornisce criteri di accesso condizionale supportati e Intune conformità dei dispositivi per Microsoft Teams Rooms. Per procedure consigliate e criteri di esempio, vedere [Accesso condizionale e procedure consigliate per la conformità Intune per Microsoft Teams Rooms](conditional-access-and-compliance-for-devices.md).

> [!NOTE]
> Teams Rooms deve essere già distribuita nei dispositivi a cui si vogliono assegnare criteri di accesso condizionale. Se non è ancora stato distribuito Teams Rooms, vedere [Creare account di risorse per sale e dispositivi Teams condivisi](with-office-365.md) e [Distribuire Microsoft Teams Rooms in Android](../devices/collab-bar-deploy.md) per altre informazioni.

## <a name="supported-conditional-access-policies"></a>Criteri di accesso condizionale supportati  

L'elenco seguente include i criteri di accesso condizionale supportati per Teams Rooms su Windows e Android. I criteri android supportati si applicano a tutti i dispositivi Android in spazi condivisi, inclusi i pannelli e i telefoni ad area comune.

| Assegnazione | Windows | Android |
|------------|---------|---------|
| Identità utente o carico di lavoro |Supportati | Supportati |
|Azioni o app cloud | Supportati <br><br> Teams Rooms deve accedere alle tre app Cloud seguenti in modalità solo Teams: Office 365 Exchange Online, Office 365 SharePoint Online e Microsoft Teams | Supportati <br><br> Teams Rooms deve accedere alle tre app Cloud seguenti in modalità solo Teams: Office 365 Exchange Online, Office 365 SharePoint Online e Microsoft Teams |
|**Condizioni**| --- | --- |
| Rischio utente | Supportati | Supportati |
| Rischio di accesso | Supportati | Supportati |
| Piattaforme per dispositivi | Supportati | Supportati |
| Posizioni | Supportati | Supportati |
|App client |Non supportato| Non supportato |
|Filtra per i dispositivi | Supportati | Supportati |
|**Concedere**| --- | --- |
| Blocca accesso | Supportati | Supportati |
| Concedere l'accesso | Supportati | Supportati | 
| Richiedere l'autenticazione a più fattori | Non supportato | Non supportato |
| Richiedere che il dispositivo sia contrassegnato come conforme | Supportati | Supportati |
|Richiedi dispositivo aggiunto a Azure AD ibrido | Non supportato | Non supportato |
|Richiedere l'app client approvata | Non supportato | Non supportato |
| Richiedi criteri di protezione delle app | Non supportato |Non supportato |
| Richiedere la modifica della password | Non supportato | Non supportato |

> [!NOTE]
> Skype for Business Online viene ritirato e non è supportato. Skype for Business'app cloud online non è supportata per i criteri di accesso condizionale basati sulla conformità dei dispositivi.

> [!NOTE]
> Microsoft Teams Rooms in Windows devono soddisfare i requisiti seguenti per supportare i controlli delle sovvenzioni per la conformità dei dispositivi:
>
> - Microsoft Teams Rooms'applicazione 4.8.19.0 o versione successiva
> - Windows 10 versione 20H2 e successive (10.0.19042)

## <a name="supported-device-compliance-policies"></a>Criteri di conformità dei dispositivi supportati 

Microsoft Teams Rooms su Windows e Teams Rooms su Android supportano criteri di conformità diversi per i dispositivi.

#### <a name="teams-rooms-on-windows"></a>[Teams Rooms Windows](#tab/mtr-w)

Di seguito è riportata una tabella delle impostazioni di conformità dei dispositivi e i suggerimenti per l'uso con Teams Rooms.  

|Criterio | Disponibilità | Note|
|---------|-------------|-------|
| [**Integrità del dispositivo**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-health) | -- | -- |
|Richiedi BitLocker| Supportati | Da usare solo se bitLocker è stato abilitato per la prima volta in Teams Rooms. |
|Richiedi l'abilitazione di Avvio protetto nel dispositivo |Supportati |L'avvio protetto è un requisito per Teams Rooms. |
|Richiedere l'integrità del codice |Supportati  | L'integrità del codice è già un requisito per Teams Rooms. |
| [**Proprietà dispositivo**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
|Versione del sistema operativo (minimo, massimo) |Non supportato | Teams Rooms aggiornamenti automatici alle versioni più recenti di Windows e l'impostazione dei valori potrebbe impedire l'accesso dopo un aggiornamento del sistema operativo.|
|Versione del sistema operativo per dispositivi mobili (minimo, massimo) | Non supportato. | N/D |
| Build del sistema operativo valide | Non supportato | N/D |
| [**Conformità Configuration Manager**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
| Richiedere la conformità del dispositivo da Configuration Manager | Supportati |  N/D |
| [**Sicurezza del sistema**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22system-security) | -- | -- |
| Tutti i criteri per le password | Non supportato | I criteri password possono impedire all'account Skype locale di eseguire automaticamente l'accesso. |
| Richiedi crittografia dell'archiviazione dei dati nel dispositivo. | Supportati  | Da usare solo se è stata abilitata la crittografia dell'archiviazione dei dati in Teams Rooms. |
| Firewall | Supportati | Il firewall è già un requisito per Teams Rooms |
| Trusted Platform Module (TPM) | Supportati | Trusted Platform Module (TPM) è già un requisito per Teams Rooms. |
| Antivirus | Supportati | L'antivirus (Windows Defender) è già un requisito per Teams Rooms. |
| Antispyware | Supportati | L'antispyware (Windows Defender) è già un requisito per Teams Rooms. |
| Microsoft Defender Antimalware | Supportati | L'antimalware di Microsoft Defender è già un requisito per Teams Rooms. |
| Versione minima antimalware di Microsoft Defender | Non supportato. | Teams Rooms aggiorna automaticamente questo componente in modo che non sia necessario impostare criteri di conformità.|
| Intelligence di sicurezza antimalware di Microsoft Defender
Aggiornato | Supportati | Verifica che l'antimalware di Microsoft Defender sia già un requisito per Teams Rooms. |
| Protezione in tempo reale | Supportati | Le protezioni in tempo reale sono già un requisito per Teams Rooms. |
| [**Microsoft Defender per endpoint**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22microsoft-defender-for-endpointws) | -- | -- |
| Richiedere che il dispositivo sia al o sotto il punteggio di rischio della macchina. | Supportati |  N/D |

#### <a name="teams-rooms-on-android"></a>[Teams Rooms su Android](#tab/mtr-a)

Di seguito è riportata una tabella delle impostazioni di conformità dei dispositivi e i suggerimenti per l'uso con Teams Rooms.  

| Criterio | Disponibilità | Note |
|---------|-------------|-------|
| [**Microsoft Defender per endpoint**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint) | -- | -- |
| Richiedere che il dispositivo sia al o sotto il punteggio di rischio della macchina | Non supportato |  N/D |
| [**Integrità del dispositivo**](/mem/intune/protect/compliance-policy-create-android%22%20/l%20%22device-health) | -- | -- |
| Dispositivo gestito con l'amministratore del dispositivo | Obbligatorio | Teams gestione dei dispositivi Android richiede l'abilitazione dell'amministratore del dispositivo. |
| Dispositivi rooted | Supportati |  N/D |
| Richiedere che il dispositivo sia a livello o sotto il livello di minaccia del dispositivo | Non supportato |  N/D |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health) | -- | -- |
| Servizi Google Play è configurato | Non supportato | Google Play non è installato in Teams dispositivi Android. |
| Provider di sicurezza aggiornato | Non supportato | Google Play non è installato in Teams dispositivi Android. |
| Analisi delle minacce nelle app | Non supportato | Google Play non è installato in Teams dispositivi Android. |
| Attestazione dispositivo SafetyNet | Non supportato | Google Play non è installato in Teams dispositivi Android.|
| [**Proprietà del dispositivo**](/mem/intune/protect/compliance-policy-create-android#device-properties) | -- | -- |
| Versione del sistema operativo (minimo, massimo) | Supportati |  N/D |
[**Sicurezza del sistema**](/mem/intune/protect/compliance-policy-create-android#system-security) | -- | -- |
| Richiedi crittografia dell'archiviazione dei dati nel dispositivo. |Supportati |  N/D |
[**Sicurezza del dispositivo**](/mem/intune/protect/compliance-policy-create-android#device-security) | -- | -- |
| Bloccare le app provenienti da origini sconosciute | Non supportato | Solo gli amministratori Teams installano app o strumenti OEM |
| integrità del runtime dell'app Portale aziendale | Supportati |  N/D|
| App con restrizioni | Non supportato |  N/D |
| Blocco del debug USB nel dispositivo | Supportati |  N/D|
[**Tutti i dispositivi Android*](/mem/intune/protect/compliance-policy-create-android#all-android-devices) | -- | -- |
|Numero massimo di minuti di inattività prima che sia necessaria la password | Non supportato |  N/D |
| Richiedere una password per sbloccare i dispositivi mobili | Non supportato | N/D |
| [**Android 10 e versioni successive**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later) | -- | -- |
| [**Android 9 e versioni precedenti o Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | -- | -- |
|Tipo di password richiesta |Non supportato | N/D|

---
