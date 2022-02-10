---
title: Crittografia end-to-end per Microsoft Teams
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 10/23/2021
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: ashgupt
description: Informazioni sulle funzionalità di crittografia avanzate in Microsoft Teams, sulla gestione della crittografia end-to-end tramite l'interfaccia di amministrazione di Teams e Microsoft PowerShell.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdce0e30c1aaa3b40f362acda47c1a9ffa35161f
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518938"
---
# <a name="use-end-to-end-encryption-for-one-to-one-microsoft-teams-calls-public-preview"></a>Usare la crittografia end-to-end per le chiamate uno-a-uno di Microsoft Teams (anteprima pubblica)

> [!IMPORTANT]
> Il modello di servizioTteams e il relativo supporto per la crittografia sono soggetti a modifiche per migliorare le esperienze dei clienti. Ad esempio, il servizio deprecazione periodica delle suite di crittografia che non sono più considerate sicure. Le modifiche apportate verranno applicate con l'obiettivo di garantire la protezione e l’affidabilità da progettazione di Teams. Inoltre, tutto il contenuto dei clienti nei data center Microsoft è crittografato. Per informazioni sui livelli di crittografia in Microsoft 365, vedere crittografia [in Microsoft 365](/microsoft-365/compliance/encryption).

La crittografia end-to-end, o E2EE, si verifica quando il contenuto viene crittografato prima che venga inviato e decrittografato solo dal destinatario previsto. Con la crittografia end-to-end, solo i due sistemi endpoint sono coinvolti nella crittografia e decrittografia dei dati della chiamata. Nessun'altra parte, inclusa Microsoft, ha accesso alla conversazione decrittografata.

Con questa versione di anteprima pubblica è in corso l'implementazione di E2EE per le chiamate uno-a-uno non pianificate. Solo il flusso multimediale in tempo reale, ovvero i dati video e vocali, per le chiamate di Teams uno-a-uno vengono crittografati end-to-end. Entrambe le parti devono attivare questa impostazione per abilitare la crittografia end-to-end. [La crittografia in Microsoft 365](/microsoft-365/compliance/encryption) protegge la chat, la condivisione di file, la presenza e altri contenuti nella chiamata.

Se non si abilita la crittografia end-to-end, Teams una chiamata o una riunione usando la crittografia in base agli standard di settore. I dati scambiati durante le chiamate sono sempre sicuri mentre sono in transito e inattivi. Per altre informazioni, vedere [Crittografia multimediale per Teams](teams-security-guide.md#media-encryption).

Durante una chiamata crittografata end-to-end, Teams le caratteristiche seguenti:

- Audio

- Video

- Condivisione dello schermo.

Le funzionalità avanzate seguenti non sono disponibili durante una chiamata E2EE:

- Sottotitoli e trascrizioni in tempo reale

- Trasferimento di chiamata

- Unione di chiamate

- Parcheggio di chiamata

- Consulta, quindi trasferisci

- Chiama complementare e trasferisci a un altro dispositivo

- Aggiunta di un partecipante

- Registrazione

Inoltre, se l'organizzazione usa la registrazione della conformità, la crittografia end-to-end non è disponibile. Per altre informazioni su come Teams supporta la registrazione della conformità, vedere [Introduzione alla registrazione basata su criteri di Teams per chiamate e riunioni](teams-recording-policy.md).

## <a name="configure-end-to-end-encryption-for-microsoft-teams"></a>Configurare la crittografia end-to-end per Microsoft Teams

Completare queste attività in modo che gli utenti possano effettuare chiamate crittografate end-to-end.

- Abilitare la crittografia end-to-end per l'organizzazione creando uno o più criteri che definiscono chi può usare la crittografia end-to-end. Prima di iniziare, assicurarsi che all'account aziendale o dell'istituto di istruzione sia stato assegnato il ruolo Teams o amministratore globale. Per informazioni, vedere [Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](using-admin-roles.md). Quando si è pronti per configurare E2EE, è possibile usare l'interfaccia di amministrazione di Teams o Microsoft PowerShell.

- Attivare le chiamate crittografate end-to-end nelle Teams nel dispositivo. Ogni utente deve completare questa attività, ma deve farlo solo su un dispositivo. Teams sincronizza questa impostazione tra gli end point supportati per ogni utente. Per istruzioni, vedere [Usare la crittografia end-to-end](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90)per Teams chiamate.

### <a name="use-the-teams-admin-center-to-configure-end-to-end-encryption"></a>Usare l'interfaccia di amministrazione di Teams per configurare la crittografia end-to-end

Il criterio predefinito globale a livello di organizzazione specifica che la crittografia end-to-end è disabilitata. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato. Per abilitare la crittografia end-to-end, creare un nuovo criterio di crittografia o modificare il criterio predefinito globale. Per abilitare la crittografia end-to-end tramite l'interfaccia di amministrazione di Teams, completare questi passaggi.

1. Usando un account aziendale o dell'istituto di istruzione a cui è stato assegnato il ruolo di amministratore di Teams o globale, accedere all'interfaccia di amministrazione di [Teams](https://admin.teams.microsoft.com/).

2. Passare a **Altre impostazioni** > **Citeri di crittografia avanzata**.

3. Scegliere il criterio predefinito oppure scegliere **Aggiungi** per aggiungere un nuovo criterio e quindi assegnare un nome al nuovo criterio.

4. Per abilitare la crittografia end-to-end per gli utenti, per la **crittografia delle chiamate end-to-end**, scegliere **gli utenti possono attivarla**, quindi scegliere **Salva**.

   Per disabilitare la crittografia end-to-end, scegliere **Disattiva per tutti.**

Dopo aver completato la configurazione del criterio, assegnare il criterio a utenti, gruppi o all'intero tenant nello stesso modo in cui si gestiscono gli altri criteri di Teams. Per informazioni sull'uso dei criteri in Teams, vedere [Gestire Teams con i criteri](manage-teams-with-policies.md).

### <a name="use-microsoft-powershell-to-configure-end-to-end-encryption"></a>Usare Microsoft PowerShell per configurare la crittografia end-to-end

È possibile gestire i criteri di crittografia end-to-end usando Microsoft PowerShell e l'interfaccia di amministrazione di Teams. Diversi cmdlet di crittografia end-to-end sono inclusi nel modulo PowerShell di Teams e documentati nel [riferimento ai cmdlet di Microsoft Teams](/powershell/teams/?view=teams-ps&preserve-view=true). Questo articolo elenca i cmdlet che è possibile usare e fornisce semplici configurazioni di esempio. Queste configurazioni usano i criteri globali predefiniti. L'organizzazione potrebbe richiedere una configurazione dei criteri più complessa. Le informazioni complete su questi cmdlet sono disponibili nelle informazioni di riferimento sui cmdlet.

Cmdlet di PowerShell per la crittografia end-to-end:

- [get-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Get-CsTeamsEnhancedEncryptionPolicy) restituisce informazioni sui criteri di crittografia avanzata di Teams nell'organizzazione.

- [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) assegna e annulla l'assegnazione di criteri di crittografia avanzata esistenti a un utente. Usare `$NULL` per annullare l'assegnazione di tutti i criteri da un utente.

- [ New-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/New-CsTeamsEnhancedEncryptionPolicy) crea un nuovo criterio di crittografia avanzata di Teams.

- [Remove-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Remove-CsTeamsEnhancedEncryptionPolicy) elimina un criterio di crittografia avanzato dall'organizzazione. Non è possibile eliminare il criterio globale predefinito.

- [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) aggiorna i valori in un criterio di crittografia avanzato di Teams esistente.

Per configurare la crittografia end-to-end, l'account aziendale o dell'istituto di istruzione deve disporre del ruolo di amministratore globale o di Teams.

#### <a name="to-enable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>Per abilitare la crittografia end-to-end per l'intero tenant usando i criteri globali

Per impostazione predefinita, la crittografia end-to-end è disabilitata. Per abilitare la crittografia end-to-end per l'intero tenant impostando il criterio globale predefinito, eseguire il cmdlet [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) come indicato di seguito.

```powershell
Set-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType DisabledUserOverride
```

Dove:

- `Global` significa che si sta impostando questa configurazione nel criterio predefinito globale a livello di organizzazione.

- `DisabledUserOverride` significa che E2EE è disabilitato in Teams per impostazione predefinita, ma gli utenti possono ignorare l'impostazione predefinita e attivare E2EE nelle impostazioni di Teams.

#### <a name="to-disable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>Per disabilitare la crittografia end-to-end per l'intero tenant usando i criteri globali

Per impostazione predefinita, la crittografia end-to-end è disabilitata. Se sono state apportate modifiche ai criteri globali, è possibile modificare nuovamente l'impostazione eseguendo il cmdlet [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) come indicato di seguito.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType Disabled
```

Dove:

- `Global` significa che si sta impostando questa configurazione nel criterio predefinito globale a livello di organizzazione.

- `Disabled` significa che si disabilita E2EE per tutti gli utenti e non è possibile attivarlo nelle impostazioni di Teams.

#### <a name="to-enable-end-to-end-encryption-for-a-single-user"></a>Per abilitare la crittografia end-to-end per un singolo utente

Per abilitare la crittografia end-to-end per un utente, eseguire il cmdlet [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) come indicato di seguito.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "username" -PolicyName "policyname"
```

Dove:

- *`username`* è il nome dell'utente.

- *`policyname`* è il nome da usare per il criterio. I nomi dei criteri non possono contenere spazi, ad esempio ContosoE2EEUserPolicy.

Gli utenti devono comunque attivare le chiamate crittografate end-to-end nelle impostazioni di Teams prima di poter effettuare una chiamata crittografata end-to-end. Per istruzioni, vedere [Usare la crittografia end-to-end](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90)per Teams chiamate.

Ad esempio:

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName "ContosoE2EEUserPolicy"
```

#### <a name="to-unassign-an-end-to-end-encryption-policy-from-a-single-user"></a>Per annullare l'assegnazione di un criterio di crittografia end-to-end da un singolo utente

Agli utenti può essere assegnato un solo criterio di crittografia alla volta. Quando si annulla l'assegnazione di un criterio a un utente, all'utente viene assegnato il criterio predefinito globale a livello di organizzazione. Non è possibile annullare l'assegnazione dei criteri predefiniti. Per annullare l'assegnazione di un criterio di crittografia end-to-end a un utente, eseguire il cmdlet [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) come indicato di seguito.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName $NULL
```

## <a name="switch-on-end-to-end-encryption-on-your-device"></a>Attivare la crittografia end-to-end nel dispositivo

Per istruzioni, vedere [Usare la crittografia end-to-end](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90)per Teams chiamate.

## <a name="related-topics"></a>Argomenti correlati

[12 principali attività per i team di sicurezza per supportare il lavoro da casa](/microsoft-365/security/top-security-tasks-for-remote-work)

[Gestire le impostazioni di riunione in Microsoft Teams](./meeting-settings-in-teams.md)
