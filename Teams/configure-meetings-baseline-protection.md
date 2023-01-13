---
title: Configurare le riunioni di Teams con la protezione di base
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Informazioni su come configurare le riunioni di Teams per un livello di protezione di base usando modelli ed etichette di riservatezza.
ms.openlocfilehash: 3770bb03c1986c4a6bbef72408340fd791b058f1
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800099"
---
# <a name="configure-teams-meetings-with-baseline-protection"></a>Configurare le riunioni di Teams con la protezione di base

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Per il livello di protezione di *base* , limiteremo gli utenti che possono evitare la sala di attesa usando un'etichetta di riservatezza e imposteremo un valore predefinito per chi può presentare con un criterio di amministrazione di Teams. È possibile limitare anche le azioni aggiuntive, se richiesto dall'organizzazione.

> [!Note]
> Le impostazioni delle riunioni nelle etichette di riservatezza e nei modelli di riunione personalizzati richiedono Teams Premium.

La tabella seguente descrive quali azioni verranno limitate per le riunioni di base e dove sono configurate queste impostazioni.

|Funzionalità|Impostazione|Posizione|Applicate|
|:------|:------|:-------|:-------|
|Consentire la fotocamera per i partecipanti|**Attivato**|Modello|No|
|Consentire il microfono per i partecipanti|**Attivato**|Modello|No|
|Applicare una filigrana al feed video di tutti gli utenti|**Disattivato**|Etichetta|Sì|
|Applicare una filigrana al contenuto condiviso|**Disattivato**|Etichetta|Sì|
|Crittografia end-to-end|**Disattivato**|Etichetta|Sì|
|Gestire ciò che i partecipanti vedono|**Disattivato**|Modello|No|
|Chat della riunione|**Attivato**|Modello|No|
|Persone chiamata in ingresso può ignorare la sala di attesa|**Disattivato**|Modello|Sì|
|Impedire la copia del contenuto della chat negli Appunti|**Disattivato**|Etichetta|Sì|
|Registra automaticamente|**Disattivato**|Modello|No|
|Chi può evitare la sala di attesa|**Persone dell'organizzazione, persone di organizzazioni attendibili e guest**|Modello|No|
|Chi può presentare|**Tutti gli utenti dell'organizzazione, ma l'utente può ignorare**|Interfaccia di amministrazione di Teams|No|
|Chi può registrare|**Organizzatori e relatori**|Modello|No|

Le impostazioni elencate come applicate vengono applicate dall'etichetta di riservatezza o dal modello di riunione. Le impostazioni non applicate possono essere modificate dall'organizzatore della riunione.

## <a name="default-values-for-who-can-present"></a>Valori predefiniti per **Chi può presentare**

Il valore predefinito per **Chi può presentare** è **Tutti**. Per il livello di protezione previsto, imposteremo un valore predefinito più sicuro di **Tutti gli utenti dell'organizzazione** che gli organizzatori della riunione possono modificare, se vogliono.

È possibile impostare questo valore con un'etichetta di riservatezza, ma il valore verrà applicato per tutte le riunioni con tale etichetta. Questa impostazione non è disponibile nei modelli di riunione, quindi verrà impostata nell'interfaccia di amministrazione di Teams.

Per configurare chi può partecipare alle riunioni
1. Nell'interfaccia di amministrazione di Teams espandere **Riunioni** e selezionare **Criteri riunione**.
1. Selezionare il criterio da aggiornare.
1. In **Partecipanti & guest** impostare **Chi può partecipare alle riunioni su** **Tutti gli utenti dell'organizzazione, ma l'utente può eseguire l'override**.
1. Selezionare **Salva**.

## <a name="watermarks-and-end-to-end-encryption"></a>Filigrane e crittografia end-to-end

Nel livello di protezione *previsto* verranno disabilitate le filigrane e la crittografia end-to-end usando un'etichetta di riservatezza. In questo modo gli organizzatori della riunione non potranno usare queste funzionalità. Le filigrane e la crittografia end-to-end sono più applicabili alle riunioni riservate.

Le filigrane e la crittografia end-to-end disabilitano alcune altre funzionalità, ad esempio la registrazione delle riunioni. Disattivandoli *per il livello* di protezione previsto, è possibile evitare le istanze in cui gli organizzatori delle riunioni usano queste funzionalità senza rendersi conto dei limiti imposti.

Se si lavora in un settore altamente regolamentato, è consigliabile mantenere queste funzionalità disponibili anche nel livello di protezione di *base* .

## <a name="sensitivity-labels"></a>Etichette di riservatezza

Per *il livello* di protezione previsto, verrà usata un'etichetta di riservatezza che è possibile usare direttamente in una riunione o come parte di un modello di riunione. A seconda della configurazione scelta, questa etichetta può essere usata anche per classificare i team e i singoli file.

Se nell'organizzazione sono già state distribuite etichette di riservatezza, considerare come si adatta questa etichetta alla strategia generale per le etichette. Se necessario, è possibile modificare il nome o le impostazioni visualizzate di seguito per soddisfare le esigenze dell'organizzazione. Se si ha già un'etichetta che si usa per la protezione di base o generale, è possibile modificare l'etichetta e aggiungervi riunioni di Teams.

Per creare un'etichetta di riservatezza
1. Aprire il [Portale di conformità di Microsoft Purview](https://compliance.microsoft.com).
1. In **Soluzioni** fare clic su **Protezione delle informazioni**.
1. Fare clic su **Crea un'etichetta**.
1. Assegnare un nome all'etichetta. È **consigliabile** l'opzione Riservato, ma è possibile scegliere un nome diverso se è già in uso.
1. Aggiungere un nome visualizzato e una descrizione e quindi fare clic su **Avanti**.
1. Nella pagina **Definire l'ambito per questa etichetta** selezionare **Elementi** e **Includi riunioni**. Se si vuole usare questa etichetta per altri scopi, è possibile selezionare altre opzioni.
1. Selezionare **Avanti**.
1. Continuare a selezionare le opzioni da usare con questa etichetta e quindi nella pagina **Impostazioni per le riunioni e le chat di Teams** scegliere i valori seguenti:
    1. Selezionare **Controlla crittografia end-to-end per il video e l'audio delle riunioni** e impostare **Applica crittografia end-to-end** su **Disattivato**.
    1. Selezionare **Controlla filigrane** e impostare **Applica filigrane al contenuto condiviso** e **Applica filigrane al feed video di tutti** gli utenti su **Disattivato**.
    1. Configurare le altre impostazioni necessarie per l'organizzazione.
    <!--:::image type="content" source="media/teams-meeting-sensitivity-label-baseline-small.png" alt-text="Screenshot of sensitivity label meeting settings." lightbox="media/teams-meeting-sensitivity-label-baseline-large.png":::-->
1. Selezionare **Avanti**.
1. Completa la procedura guidata con le impostazioni aggiuntive che vuoi usare, quindi seleziona **Crea etichetta** e quindi fai clic su **Fine**.

Dopo aver creato l'etichetta, è necessario pubblicarla agli utenti che la useranno. Per la protezione di base, l'etichetta sarà disponibile per tutti gli utenti. L'etichetta viene pubblicata nel Portale di conformità di Microsoft Purview nella scheda **Criteri etichetta** della pagina **Protezione delle informazioni**. Se si ha un criterio esistente applicabile a tutti gli utenti, aggiungere questa etichetta a tale criterio. Se è necessario creare un nuovo criterio, vedere [Pubblicare etichette di riservatezza creando un criterio di etichetta](/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

Per altre informazioni sull'uso di etichette di riservatezza con le riunioni, vedere [Usare le etichette di riservatezza per proteggere gli elementi del calendario, le riunioni e le chat di Teams](/microsoft-365/compliance/sensitivity-labels-meetings).

## <a name="meeting-templates"></a>Modelli di riunione

Nel *livello di* protezione previsto, useremo il modello per impostare un valore predefinito per chi può ignorare la sala di attesa che include partecipanti esterni da domini attendibili.

Impediamo inoltre alle persone che accedono tramite telefono di ignorare la sala d'attesa. È possibile omettere questa impostazione se l'organizzazione organizza spesso riunioni in cui i partecipanti esterni dovrebbero essere in grado di partecipare direttamente. Se esistono determinati tipi di riunioni in cui ciò è vero, è consigliabile usare un modello separato per tali riunioni.

Se si è scelto di disabilitare le filigrane e la crittografia end-to-end per la riservatezza, è anche possibile usare il modello per nascondere queste impostazioni all'organizzatore della riunione.

Per creare un modello di riunione personalizzato

1. Nell'interfaccia di amministrazione di Teams espandere **Riunioni** e selezionare **Modelli di riunione**.
1. Seleziona **Aggiungi**
1. Digitare un nome e una descrizione per il modello.
1. Nella sezione **Applica etichetta di riservatezza** scegliere l'etichetta creata sopra.
1. Seleziona **Applica etichetta di riservatezza** e quindi **seleziona Blocca**.
1. Nell'elenco a discesa **Sala di attesa** selezionare **Tutti gli utenti dell'organizzazione, organizzazioni attendibili e guest**.
1. Assicurati che **Persone chiamata nel telefono possa ignorare la sala di attesa** sia impostata su **Disattivato**, quindi selezionala e seleziona **Blocca**.
1. Se le filigrane e la crittografia end-to-end sono state disabilitate con l'etichetta di riservatezza, è consigliabile selezionarle qui e selezionare **Nascondi** in modo che gli organizzatori delle riunioni non le vedano.
1. Modificare eventuali impostazioni aggiuntive, se necessario.
1. Per impedire all'organizzatore della riunione di modificare un'impostazione, selezionarla e quindi selezionare **Blocca**.
1. Per impedire all'organizzatore della riunione di visualizzare un'impostazione, selezionarla e quindi scegliere **Nascondi**.
1. Selezionare **Salva**.

## <a name="related-topics"></a>Argomenti correlati

[Configurare le riunioni di Teams con tre livelli di protezione](configure-meetings-three-tiers-protection.md)

[Panoramica dei modelli di riunione personalizzati in Microsoft Teams](custom-meeting-templates-overview.md)

[Usare i modelli di riunione di Teams, le etichette di riservatezza e i criteri di amministrazione insieme per le riunioni riservate](meeting-templates-sensitivity-labels-policies.md)
