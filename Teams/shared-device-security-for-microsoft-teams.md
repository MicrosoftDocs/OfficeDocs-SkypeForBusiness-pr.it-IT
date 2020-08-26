---
title: Guida alla sicurezza di Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Indicazioni per l'uso sicuro di Microsoft Teams con un computer condiviso sul luogo di lavoro.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3486df0ca12303a9351c756df4184f160e95ab34
ms.sourcegitcommit: 32023931b607542cffadef74383e3ecd47db4ab6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868695"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a>Usare Microsoft teams in modo sicuro sui computer condivisi

Se possibile, *si raccomanda* alle organizzazioni di adottare un approccio Zero Trust per i dispositivi client, usando le funzionalità di gestione dei dispositivi, i controlli dell'integrità dei dispositivi, l'applicazione dei criteri, la crittografia a livello dei dispositivi e altre funzionalità di sicurezza.

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="Immagine dell'architettura Zero Trust che mostra la verifica esplicita, il principio del privilegio minimo e la presunzione della violazione, ossia i principi fondamentali dell'approccio Zero Trust, nei cerchi blu.":::

Gli amministratori possono creare ambienti molto sicuri *concentrandosi* sulla verifica, il principio del privilegio minimo e la presunzione della violazione: sono standard che comportano azioni che riducono al minimo i rischi per utenti e dati. 

> [!TIP]
> Per un'analisi più approfondita dell'architettura Zero Trust, vedere [questi video](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a>Suggerimenti per usare Microsoft Teams in modo sicuro con un computer condiviso

Pur riconoscendo che potrebbe non essere possibile o praticabile in tutti gli scenari, è comunque importante che gli amministratori di sicurezza seguano le indicazioni per usare Teams con un computer condiviso o un dispositivo non gestito nel migliore dei modi.

Si consiglia di sviluppare piani per rispettare le linee guida nel modo più rigoroso possibile.

1. Usare le funzionalità di sicurezza della piattaforma del sistema operativo.
    1. Assicurarsi che il sistema operativo sia configurato in modo da installare gli aggiornamenti automatici distribuiti dal provider del sistema operativo (per i sistemi Microsoft, ciò può essere fatto tramite [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)). 
    2. Assicurarsi che le funzionalità crittografiche del dispositivo, come [**bitlocker**](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview), siano abilitate, e che la chiave usata per accedere al dispositivo sia protetta.  Si noti che la maggior parte dei [**dispositivi Windows 10 moderni supporta BitLocker**](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10) 
    1. Usare le funzionalità antivirus, come quelle offerte da [**Windows Defender**](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), sul proprio dispositivo.
    1. L'uso di [account utente separati](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) per ogni utente del sistema è fortemente raccomandato.
    1. *Non* concedere né usare i privilegi di amministrazione per funzioni non amministrative (come navigare su internet, eseguire Teams, ecc.).

2. Sfruttare le funzionalità di sicurezza del browser.
    1. Usare le sessioni di navigazione privata per minimizzare i dati e la cronologia che persistono sul disco. Per esempio, usare la [navigazione inPrivate di Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [la navigazione in incognito di Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en), o le funzionalità di navigazione privata del browser in uso. 
    1. Si raccomanda di modificare il sistema in modo che la navigazione privata sia attivata per *impostazione predefinita*. 

3. Individuare e usare [l'app web di Teams](https://teams.microsoft.com) (indicata a volte come il *client web*), invece del client scaricabile di Teams.

4. Dopo aver finito di usare il sistema condiviso, è necessario: 
    1. [Disconnettersi da Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).
    1. Chiudere tutte le schede e le finestre del browser.
    1. Disconnettersi dal dispositivo.

Gli elementi precedenti non sono un elenco completo delle migliori pratiche o dei controlli di sicurezza relativi a tutti i casi, e potrebbe essere possibile compiere altre azioni nel proprio ambiente (ad esempio, gli amministratori di sicurezza possono scegliere di usare i collegamenti e gli allegati sicuri di Teams se usano [Office 365 ATP piano 1 o 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)). Tuttavia, questi passaggi sono un punto di partenza per creare indicazioni per l'uso di Teams con dispositivi condivisi.

## <a name="more-information"></a>Altre informazioni

[Bitlocker in Gestione configurazione](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[BitLocker per Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/encrypt-devices)

[Sicurezza degli endpoint in Intune](https://docs.microsoft.com/mem/intune/protect/endpoint-security)

[Abilitare](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender in Sicurezza di Windows ed [eseguire le scansioni](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)

[Articolo su Centro sicurezza di Microsoft Defender ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[Client web e app web di Teams](https://docs.microsoft.com/microsoftteams/get-clients#web-client)

[Sicurezza e Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-security-guide)
