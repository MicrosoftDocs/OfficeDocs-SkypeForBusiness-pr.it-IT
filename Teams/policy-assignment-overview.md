---
title: Assegnare criteri in Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni sui diversi modi per assegnare criteri e pacchetti di criteri a utenti e gruppi in Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: fb85ae05925a44db75ed63ada899c6fca92cbceb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621988"
---
# <a name="assign-policies-in-teams--getting-started"></a>Assegnare criteri in Teams - Guida introduttiva

Gli amministratori usano i criteri per controllare le Teams disponibili per gli utenti dell'organizzazione. Ad esempio, ci sono criteri di chiamata, criteri riunione e criteri di messaggistica, per cita solo alcuni.

Le organizzazioni hanno diversi tipi di utenti con esigenze specifiche. I criteri personalizzati creati e assegnati consentono di personalizzare le impostazioni dei criteri per diversi set di utenti in base a tali esigenze.

Per gestire facilmente i criteri nell'organizzazione, Teams diversi modi per assegnare criteri agli utenti. Assegnare un criterio direttamente agli utenti, singolarmente o su scala tramite un'assegnazione batch o a un gruppo di cui gli utenti sono membri. È anche possibile usare i pacchetti di criteri per assegnare una raccolta predefinita di criteri agli utenti dell'organizzazione con ruoli simili. L'opzione scelta dipende dal numero di criteri che si stanno gestendo e dal numero di utenti a cui si stanno assegnando i criteri. I criteri globali (predefiniti a livello di organizzazione) si applicano al maggior numero di utenti dell'organizzazione. È necessario assegnare criteri solo agli utenti che richiedono criteri specializzati.

Questo articolo descrive i diversi modi in cui è possibile assegnare criteri agli utenti e gli scenari consigliati per l'uso.

Per informazioni dettagliate su come **assegnare criteri a utenti** e gruppi, vedere Assegnazione [di criteri a utenti e gruppi.](assign-policies-users-and-groups.md) Per informazioni dettagliate su come **assegnare pacchetti di criteri,** vedere [Assegnare pacchetti di criteri.](assign-policy-packages.md)

## <a name="which-policy-takes-precedence"></a>Quali criteri hanno la precedenza?

Un utente ha un criterio efficace per ogni tipo di criterio. È possibile, o anche probabile, che a un utente sia assegnato direttamente un criterio ed è anche membro di uno o più gruppi a cui è assegnato un criterio dello stesso tipo. In questi tipi di scenari, quali criteri hanno la precedenza? I criteri effettivi di un utente vengono determinati in base alle regole di precedenza, come indicato di seguito.

Se a un utente viene assegnato direttamente un criterio (singolarmente o tramite un'assegnazione batch), tale criterio ha la precedenza. Nell'esempio visivo seguente, i criteri effettivi dell'utente sono i criteri di riunione di Lincoln Square, assegnati direttamente all'utente.

![Diagramma che mostra la precedenza di un criterio assegnato direttamente](media/assign-policies-example-directly-assigned.png)

Se a un utente non è assegnato direttamente un criterio di un determinato tipo, il criterio assegnato a un gruppo di cui l'utente è membro ha la precedenza. Se un utente è membro di più gruppi, ha la precedenza il criterio che ha la classificazione più alta[(](assign-policies-users-and-groups.md#group-assignment-ranking)classificazione assegnazione gruppo ) per il tipo di criterio specificato.

In questo esempio visivo, i criteri effettivi dell'utente sono i criteri Exec Teams e HD, che hanno la classificazione di assegnazione più alta rispetto ad altri gruppi di cui l'utente è membro e a cui è assegnato anche un criterio dello stesso tipo di criteri.  

![Diagramma che mostra la precedenza di un criterio ereditato dal gruppo](media/assign-policies-example-group.png)

Se a un utente non è assegnato direttamente un criterio o non è membro di alcun gruppo a cui è assegnato un criterio, l'utente ottiene il criterio globale (impostazione predefinita a livello di organizzazione) per quel tipo di criterio. Ecco un esempio visivo.

![Diagramma che mostra la precedenza di un criterio globale](media/assign-policies-example-global.png)

Per altre informazioni, vedere ([Regole di precedenza](assign-policies-users-and-groups.md#precedence-rules)).

## <a name="ways-to-assign-policies"></a>Modi per assegnare criteri

Ecco una panoramica dei modi in cui è possibile assegnare criteri agli utenti e degli scenari consigliati per ognuno di essi. Selezionare i collegamenti per altre informazioni.

Prima di assegnare criteri a singoli utenti o gruppi, impostare i criteri globali (predefiniti a livello di [organizzazione)](#set-the-global-policies) in modo che siano applicabili al maggior numero di utenti dell'organizzazione.  Dopo aver impostato i criteri globali, sarà necessario assegnare i criteri solo agli utenti che richiedono criteri specializzati.

|Eseguire questa operazione  |Se...  | Uso in corso...
|---------|---------|----|
|[Assegnare un criterio a singoli utenti](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | Non si ha la Teams per iniziare o è sufficiente assegnare uno o un paio di criteri a un numero limitato di utenti. |L Microsoft Teams di amministrazione o i cmdlet di PowerShell nel modulo Teams PowerShell
|[Assegnare un criterio a un gruppo](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |Assegnare criteri in base all'appartenenza al gruppo di un utente. Ad esempio, assegnare un criterio a tutti gli utenti di un gruppo di sicurezza o di una lista di distribuzione.| L Microsoft Teams di amministrazione o i cmdlet di PowerShell nel modulo Teams PowerShell|
|[Assegnare un criterio a un batch di utenti](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | Assegnare criteri a set di utenti di grandi dimensioni. Ad esempio, assegnare un criterio a centinaia o migliaia di utenti dell'organizzazione contemporaneamente. |L Microsoft Teams di amministrazione o i cmdlet di PowerShell nel modulo Teams PowerShell|
|[Assegnare un pacchetto di criteri agli utenti](assign-policy-packages.md#assign-a-policy-package-to-users)  |Assegnare più criteri a set specifici di utenti dell'organizzazione con ruoli uguali o simili. Ad esempio, assegnare il pacchetto di criteri Education (Teacher) agli insegnanti dell'istituto di istruzione per concedere loro l'accesso completo a chat, chiamate e riunioni. Assegnare il pacchetto di criteri Education (Secondary school student) agli studenti secondari per limitare determinate funzionalità, ad esempio le chiamate private.  |L Microsoft Teams di amministrazione o i cmdlet di PowerShell nel modulo Teams PowerShell|
|[Assegnare un pacchetto di criteri a un gruppo](assign-policy-packages.md#assign-a-policy-package-to-a-group) (in anteprima privata)   |Assegnare più criteri a un gruppo di utenti dell'organizzazione con ruoli uguali o simili. Ad esempio, assegnare un pacchetto di criteri a tutti gli utenti di un gruppo di sicurezza o di una lista di distribuzione. |L Microsoft Teams di amministrazione di PowerShell (disponibile a breve) o i cmdlet di PowerShell nel modulo Teams PowerShell|
|[Assegnare un pacchetto di criteri a un batch di utenti](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|Assegnare più criteri a un batch di utenti dell'organizzazione con ruoli uguali o simili. Ad esempio, assegnare il pacchetto di criteri Education (Teacher) a tutti gli insegnanti dell'istituto di istruzione usando l'assegnazione batch per concedere loro l'accesso completo a chat, chiamate e riunioni. Assegnare il pacchetto di criteri Education (Secondary school student) a un batch di studenti secondari per limitare determinate funzionalità, ad esempio le chiamate private.|Cmdlet di PowerShell nel modulo Teams PowerShell|

## <a name="set-the-global-policies"></a>Impostare i criteri globali

Seguire questa procedura per impostare i criteri globali (predefiniti a livello di organizzazione) per ogni tipo di criterio.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare alla pagina dei criteri per il tipo di criterio da aggiornare. Ad **esempio,** Teams  >  **Teams,** Criteri riunioni riunioni, Criteri  >   **di messaggistica** o **Criteri chiamate**  >  **vocali.**
2. Selezionare il **criterio Globale (impostazione predefinita** a livello di organizzazione) per visualizzare le impostazioni correnti.
3. Aggiornare il criterio in base alle esigenze e quindi selezionare **Applica**.

![Aggiornare i criteri globali nell'Teams di amministrazione](media/assign-globalpolicy.png)

### <a name="using-powershell"></a>Utilizzo di PowerShell

Per impostare i criteri globali con PowerShell, usare l'identificatore globale.  Per iniziare, esaminare i criteri globali correnti per determinare l'impostazione da modificare.

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

Aggiornare quindi i criteri globali in base alle esigenze.  È necessario specificare solo i valori per le impostazioni da modificare.

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="view-your-policy-assignments-in-the-activity-log"></a>Visualizzare le assegnazioni dei criteri nel log attività

Quando si assegnano criteri agli utenti nell Microsoft Teams di amministrazione, è possibile visualizzare lo stato di tali assegnazioni di criteri nel log attività. Il log attività mostra le assegnazioni dei criteri a batch di più di 20 utenti tramite l'Microsoft Teams di amministrazione degli ultimi 30 giorni. Tenere presente che il log attività non mostra le assegnazioni dei pacchetti di criteri, le assegnazioni dei criteri a batch di meno di 20 utenti tramite l'interfaccia di amministrazione di Microsoft Teams o le assegnazioni dei criteri tramite PowerShell.

![Screenshot della pagina Log attività](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Visualizzare le attività di assegnazione dei criteri nel log attività

Per visualizzare le assegnazioni dei criteri nel log attività:

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare a **Dashboard** e quindi in **Log attività** selezionare **Visualizza dettagli.**
2. È possibile visualizzare tutte le assegnazioni dei criteri o filtrare l'elenco in base allo stato per visualizzare solo le assegnazioni non **avviate,** **in** corso o **completate.** Verranno visualizzate le informazioni seguenti su ogni attività:
    - **Nome:** nome dell'assegnazione dei criteri. Fare clic sul collegamento per visualizzare altri dettagli. Questo include il numero di utenti a cui è stato assegnato il criterio e il numero di assegnazioni completate, in corso e non avviate. Verranno visualizzati anche l'elenco degli utenti nel batch e lo stato e il risultato per ogni utente. Ecco un esempio:

        ![Screenshot del pulsante](media/activity-log-policy-assignment-detail.png)

    - **Inviato:** data e ora di invio dell'assegnazione dei criteri.
    - **Ora di completamento:** data e ora di completamento dell'assegnazione dei criteri.
    - **Impatto su:** numero di utenti nel batch.
    - **Stato generale:** stato dell'assegnazione dei criteri.

> [!NOTE]
> È anche possibile accedere al log attività dalla **pagina** Utenti. Dopo aver fatto **clic su Applica** per inviare un'assegnazione di criteri in blocco, nella parte superiore della pagina verrà visualizzato un banner. Fare clic **sul collegamento Log** attività nel banner.

## <a name="related-topics"></a>Argomenti correlati

- [Assegnare criteri a utenti e gruppi](assign-policies-users-and-groups.md)
- [Assegnare pacchetti di criteri a utenti e gruppi](assign-policy-packages.md)
- [Gestire Teams con i criteri](manage-teams-with-policies.md)
- [Teams Panoramica di PowerShell](teams-powershell-overview.md)