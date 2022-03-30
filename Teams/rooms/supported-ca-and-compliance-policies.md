---
title: Criteri di conformità dei dispositivi di Intune e accesso condizionale supportati per Microsoft Teams Rooms
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
description: Informazioni sui criteri di accesso condizionale e conformità dei dispositivi intune supportati e consigliati per Microsoft Teams Rooms.
ms.openlocfilehash: ea27f71a7d4f64bc1d9e8c8a3cd3d7b2a52151f3
ms.sourcegitcommit: ecc67b7b9378cc72f85517f30c32680045056fda
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2022
ms.locfileid: "64504196"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms"></a>Criteri di conformità dei dispositivi di Intune e accesso condizionale supportati per Microsoft Teams Rooms

Questo articolo fornisce i criteri di conformità dei dispositivi di Intune e accesso condizionale supportati per Microsoft Teams Rooms. Per le procedure consigliate e i criteri di esempio, vedere [Procedure consigliate per l'accesso condizionale e la conformità di Intune per Microsoft Teams Rooms](conditional-access-and-compliance-for-devices.md).

> [!NOTE]
> Teams Rooms deve essere già distribuito nei dispositivi a cui si vogliono assegnare i criteri di accesso condizionale. Se non è ancora stata distribuita Teams Rooms, vedere Creare account delle risorse per le chat room e i dispositivi [Teams](with-office-365.md) condivisi e Distribuire Microsoft Teams Rooms in [Android](../devices/collab-bar-deploy.md) per altre informazioni.

## <a name="supported-conditional-access-policies"></a>Criteri di accesso condizionale supportati  

L'elenco seguente include i criteri di accesso condizionale supportati per Teams Rooms in Windows e android. I criteri di Android supportati si applicano a tutti i dispositivi, i telefoni e i pannelli Android.

| Assegnazione | Windows | Android |
|------------|---------|---------|
| Identità degli utenti o del carico di lavoro |Supportato | Supportato |
|App o azioni nel cloud | Supportato <br><br> Teams Rooms accedere alle tre app Cloud seguenti in modalità solo Teams: Office 365 Exchange Online, Office 365 SharePoint Online e Microsoft Teams | Supportato <br><br> Teams Rooms accedere alle tre app Cloud seguenti in modalità solo Teams: Office 365 Exchange Online, Office 365 SharePoint Online e Microsoft Teams |
|**Condizioni**| --- | --- |
| Rischio per gli utenti | Supportato | Supportato |
| Rischio di accesso | Supportato | Supportato |
| Piattaforme per dispositivi | Supportato | Supportato |
| Posizioni | Supportato | Supportato |
|App client |Non supportato| Non supportato |
|Filtrare per i dispositivi | Supportato | Supportato |
|**Concedi**| --- | --- |
| Bloccare l'accesso | Supportato | Supportato |
| Concedere l'accesso | Supportato | Supportato | 
| Richiedere l'autenticazione a più fattori | Non supportato | Non supportato |
| Richiedi che il dispositivo sia contrassegnato come conforme | Supportato | Supportato |
|Richiedi connessione ibrida Azure AD aggiunto al dispositivo | Non supportato | Non supportato |
|Richiedi app client approvata | Non supportato | Non supportato |
| Richiedi criteri di protezione delle app | Non supportato |Non supportato |
| Richiedere la modifica della password | Non supportato | Non supportato |

> [!NOTE]
> Skype for Business Online è ritirato e non è supportato. Skype for Business'app cloud online non è supportata per i criteri di accesso condizionale basati sulla conformità dei dispositivi.

> [!NOTE]
> Microsoft Teams Rooms in Windows devono soddisfare i requisiti seguenti per supportare i controlli di concessione della conformità dei dispositivi:
>
> - Microsoft Teams Rooms 4.8.19.0 o versioni successive
> - Windows 10 versione 20H2 e successive (10.0.19042)

## <a name="supported-device-compliance-policies"></a>Criteri di conformità dei dispositivi supportati 

Microsoft Teams Rooms in Windows e Teams Rooms android supportano criteri di conformità dei dispositivi diversi.

#### <a name="teams-rooms-on-windows"></a>[Teams Rooms in Windows](#tab/mtr-w)

Di seguito è riportata una tabella delle impostazioni di conformità dei dispositivi e dei consigli per l'uso con Teams Rooms.  

|Criterio | Disponibilità | Note|
|---------|-------------|-------|
| [**Integrità del dispositivo**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-health) | -- | -- |
|Richiedi BitLocker| Supportato | Usare solo se BitLocker è stato abilitato per la prima volta Teams Rooms. |
|Richiedi l'a attivazione dell'avvio sicuro nel dispositivo |Supportato |Secure Boot è un requisito per Teams Rooms. |
|Richiedere l'integrità del codice |Supportato  | L'integrità del codice è già un requisito per Teams Rooms. |
| [**Proprietà dispositivo**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
|Versione del sistema operativo (minimo, massimo) |Non supportato | Teams Rooms aggiornamenti automatici alle versioni più recenti di Windows e l'impostazione dei valori qui potrebbe impedire l'accesso riuscito dopo un aggiornamento del sistema operativo.|
|Versione del sistema operativo per dispositivi mobili (minimo, massimo) | Non supportato. | N/D |
| Build del sistema operativo valide | Non supportato | N/D |
| [**Conformità di Configuration Manager**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
| Richiedere la conformità dei dispositivi da Configuration Manager | Supportato |  N/D |
| [**Sicurezza del sistema**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22system-security) | -- | -- |
| Tutti i criteri password | Non supportato | I criteri password possono impedire l'accesso Skype'account locale. |
| Richiedere la crittografia dell'archiviazione dei dati nel dispositivo. | Supportato  | Da usare solo se è stata abilitata per la prima volta la crittografia dell'archiviazione dei dati Teams Rooms. |
| Firewall | Supportato | Il firewall è già un requisito per Teams Rooms |
| TPM (Trusted Platform Module) | Supportato | Il TPM (Trusted Platform Module) è già un requisito per Teams Rooms. |
| Antivirus | Supportato | L'antivirus (Windows Defender) è già un requisito per Teams Rooms. |
| Antispyware | Supportato | Antispyware (Windows Defender) è già un requisito per Teams Rooms. |
| Microsoft Defender Antimalware | Supportato | Microsoft Defender Antimalware è già un requisito per Teams Rooms. |
| Versione minima di Microsoft Defender Antimalware | Non supportato. | Teams Rooms aggiorna automaticamente questo componente in modo che non sia necessario impostare criteri di conformità.|
| Microsoft Defender Antimalware Security Intelligence
aggiornato | Supportato | Verificare che Microsoft Defender Antimalware sia già un requisito per Teams Rooms. |
| Protezione in tempo reale | Supportato | Le protezioni in tempo reale sono già un requisito per Teams Rooms. |
| [**Microsoft Defender per endpoint**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22microsoft-defender-for-endpointws) | -- | -- |
| Richiedere che il dispositivo sia in corrispondenza o sotto il punteggio di rischio della macchina. | Supportato |  N/D |

#### <a name="teams-rooms-on-android"></a>[Teams Rooms su Android](#tab/mtr-a)

Di seguito è riportata una tabella delle impostazioni di conformità dei dispositivi e dei consigli per l'uso con Teams Rooms.  

| Criterio | Disponibilità | Note |
|---------|-------------|-------|
| [**Microsoft Defender per endpoint**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint) | -- | -- |
| Richiedere che il dispositivo sia in corrispondenza o sotto il punteggio di rischio della macchina | Non supportato |  N/D |
| [**Integrità del dispositivo**](/mem/intune/protect/compliance-policy-create-android%22%20/l%20%22device-health) | -- | -- |
| Dispositivo gestito con l'amministratore del dispositivo | Non supportato. | Teams i dispositivi Android vengono gestiti con il dispositivo
amministratore. |
| Dispositivi con radice | Supportato |  N/D |
| Richiedere che il dispositivo sia al livello di minaccia del dispositivo o che sia al di sotto del livello di minaccia | Non supportato |  N/D |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health) | -- | -- |
| Google Play Services è configurato | Non supportato | Google Play non è installato nei Teams Android. |
| Provider di sicurezza aggiornato | Non supportato | Google Play non è installato nei Teams Android. |
| Analisi delle minacce nelle app | Non supportato | Google Play non è installato nei Teams Android. |
| Attestazione del dispositivo SafetyNet | Non supportato | Google Play non è installato nei Teams Android.|
| [**Proprietà del dispositivo**](/mem/intune/protect/compliance-policy-create-android#device-properties) | -- | -- |
| Versione del sistema operativo (minimo, massimo) | Supportato |  N/D |
[**Sicurezza del sistema**](/mem/intune/protect/compliance-policy-create-android#system-security) | -- | -- |
| Richiedere la crittografia dell'archiviazione dei dati nel dispositivo. |Supportato |  N/D |
[**Sicurezza del dispositivo**](/mem/intune/protect/compliance-policy-create-android#device-security) | -- | -- |
| Bloccare le app da origini sconosciute | Non supportato | Solo Teams amministratori installano app o strumenti OEM |
| Portale aziendale'integrità di runtime dell'app | Supportato |  N/D|
| App con restrizioni | Non supportato |  N/D |
| Bloccare il debug USB nel dispositivo | Supportato |  N/D|
[**Tutti i dispositivi Android*](/mem/intune/protect/compliance-policy-create-android#all-android-devices) | -- | -- |
|Numero massimo di minuti di inattività prima che la password sia obbligatoria | Non supportato |  N/D |
| Richiedere una password per sbloccare i dispositivi mobili | Non supportato | N/D |
| [**Android 10 e versioni successive**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later) | -- | -- |
| [**Android 9 e versioni precedenti o Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | -- | -- |
|Tipo di password obbligatorio |Non supportato | N/D|

---
