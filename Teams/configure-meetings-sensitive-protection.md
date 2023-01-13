---
title: Configurare le riunioni di Teams con la protezione dei dati sensibili
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
description: Informazioni su come configurare le riunioni di Teams per la protezione delle informazioni riservate usando modelli ed etichette di riservatezza.
ms.openlocfilehash: 3aae927f29464f3e5d8a9e695c170ded06d3dd1f
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800089"
---
# <a name="configure-teams-meetings-with-protection-for-sensitive-data"></a>Configurare le riunioni di Teams con la protezione dei dati sensibili

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Per il livello di protezione *dei dati riservati* , limiteremo gli utenti che possono ignorare la sala di attesa, chi può presentare e chi può registrare. È possibile limitare anche le azioni aggiuntive, se richiesto dall'organizzazione.

La tabella seguente descrive le azioni che verranno limitate per le riunioni riservate e le impostazioni configurate.

|Funzionalità|Impostazione|Posizione|Applicate|
|:------|:------|:-------|:-------|
|Consentire la fotocamera per i partecipanti|**Attivato**|Modello|No|
|Consentire il microfono per i partecipanti|**Attivato**|Modello|No|
|Applicare una filigrana al feed video di tutti gli utenti|**Disattivato**|Modello|No|
|Applicare una filigrana al contenuto condiviso|**Disattivato**|Modello|No|
|Crittografia end-to-end|**Disattivato**|Modello|No|
|Gestire ciò che i partecipanti vedono|**Attivato**|Modello|No|
|Chat della riunione|**Attivato**|Modello|No|
|Persone chiamata in ingresso può ignorare la sala di attesa|**Disattivato**|Modello|Sì|
|Impedire la copia del contenuto della chat negli Appunti|**Disattivato**|Etichetta|No|
|Registra automaticamente|**Disattivato**|Modello|No|
|Chi può evitare la sala di attesa|**Solo le persone invitate**|Etichetta|Sì|
|Chi può presentare|**Utenti dell’organizzazione e guest**|Etichetta|Sì|
|Chi può registrare|**Organizzatori e co-organizzatori**|Etichetta|Sì|

Le impostazioni elencate come applicate vengono applicate dall'etichetta di riservatezza o dal modello di riunione. Le impostazioni non applicate possono essere modificate dall'organizzatore della riunione.

> [!Note]
> Le impostazioni delle riunioni nelle etichette di riservatezza e nei modelli di riunione personalizzati richiedono Teams Premium.

## <a name="presentation-options-for-sensitive-meetings"></a>Opzioni di presentazione per riunioni riservate

Per il livello di protezione dei dati *riservati* , stiamo applicando impostazioni specifiche per gli utenti che possono presentare e per la modalità di condivisione del contenuto.

Attivando **Gestisci ciò che i partecipanti possono vedere**, ci assicuriamo che gli organizzatori della riunione possano controllare i contenuti condivisi prima che vengano visualizzati sullo schermo per i partecipanti. In questo esempio viene usato un modello per attivare questa opzione per impostazione predefinita, ma è anche possibile applicarlo nel modello, se necessario.

Impostando **Chi può presentare** per **Persone nell'organizzazione e gli utenti guest** nell'etichetta di riservatezza, viene eliminata la possibilità che partecipanti anonimi presentino durante la riunione. È possibile limitare ulteriormente questa opzione solo agli **organizzatori e ai co-organizzatori** , se necessario. Lo faremo per il livello di protezione *altamente sensibile* .

La registrazione verrà limitata anche agli organizzatori e ai co-organizzatori usando l'etichetta di riservatezza.

## <a name="lobby-options-for-sensitive-meetings"></a>Opzioni di sala di attesa per riunioni sensibili

Useremo l'etichetta di riservatezza per impedire a chiunque non sia stato invitato partecipanti (persone direttamente invitate dall'organizzatore o a cui è stato inoltrato un invito) di ignorare la sala di attesa. Questo offre un ulteriore livello di protezione consentendo all'organizzatore di controllare chiunque non abbia inviato direttamente un invito prima di ammetterlo alla riunione. È possibile limitare ulteriormente questa impostazione scegliendo **Solo organizzatori e co-organizzatori**. Lo faremo per il livello di protezione *altamente sensibile* .


## <a name="sensitivity-labels"></a>Etichette di riservatezza

Per il livello di protezione dei dati sensibili, useremo un'etichetta di riservatezza che è possibile usare direttamente in una riunione o come parte di un modello di riunione. A seconda della configurazione scelta, questa etichetta può essere usata anche per classificare i team e i singoli file.

Se nell'organizzazione sono già state distribuite etichette di riservatezza, considerare come si adatta questa etichetta alla strategia generale per le etichette. Se necessario, è possibile modificare il nome o le impostazioni per soddisfare le esigenze dell'organizzazione. Se hai già un'etichetta che usi per informazioni riservate, puoi modificare l'etichetta e aggiungervi riunioni di Teams.

Per creare un'etichetta di riservatezza
1. Aprire il [Portale di conformità di Microsoft Purview](https://compliance.microsoft.com).
1. In **Soluzioni** fare clic su **Protezione delle informazioni**.
1. Fare clic su **Crea un'etichetta**.
1. Assegnare un nome all'etichetta. È **consigliabile** l'opzione Riservato, ma è possibile scegliere un nome diverso se è già in uso.
1. Aggiungere un nome visualizzato e una descrizione e quindi fare clic su **Avanti**.
1. Nella pagina **Definire l'ambito per questa etichetta** selezionare **Elementi** e **Includi riunioni**. Se si vuole usare questa etichetta per altri scopi, è possibile selezionare altre opzioni.
1. Selezionare **Avanti**.
1. Continuare a selezionare le opzioni da usare con questa etichetta e quindi nella pagina **Impostazioni per le riunioni e le chat di Teams** scegliere i valori seguenti:
    1. Selezionare **Controlla chi può ignorare la sala di attesa** e scegliere **Solo le persone invitate** dall'elenco a discesa.
    1. Selezionare **Controlla chi può presentare** e scegliere **Persone dell'organizzazione e degli utenti guest** nell'elenco a discesa.
    1. Selezionare **Chi può registrare** e scegliere **Organizzatori e co-organizzatori** nell'elenco a discesa.
    1. Configurare le altre impostazioni necessarie per l'organizzazione.
    <!--:::image type="content" source="media/teams-meeting-sensitivity-label-sensitive-small.png" alt-text="Screenshot of sensitivity label meeting settings." lightbox="media/teams-meeting-sensitivity-label-sensitive-large.png":::-->
1. Selezionare **Avanti**.
1. Completa la procedura guidata con le impostazioni aggiuntive che vuoi usare, quindi seleziona **Crea etichetta** e quindi fai clic su **Fine**.

Dopo aver creato l'etichetta, è necessario pubblicarla agli utenti che la useranno. Per la protezione dei dati sensibili, l'etichetta verrà reso disponibile a tutti gli utenti. L'etichetta viene pubblicata nel Portale di conformità di Microsoft Purview nella scheda **Criteri etichetta** della pagina **Protezione delle informazioni**. Se si ha un criterio esistente applicabile a tutti gli utenti, aggiungere questa etichetta a tale criterio. Se è necessario creare un nuovo criterio, vedere [Pubblicare etichette di riservatezza creando un criterio di etichetta](/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

Per altre informazioni sull'uso di etichette di riservatezza con le riunioni, vedere [Usare le etichette di riservatezza per proteggere gli elementi del calendario, le riunioni e le chat di Teams](/microsoft-365/compliance/sensitivity-labels-meetings).

## <a name="meeting-templates"></a>Modelli di riunione

Un vantaggio dell'uso dei modelli è la possibilità di creare più modelli che usano la stessa etichetta di riservatezza per bloccare impostazioni diverse. Ad esempio, se alcune riunioni sensibili sono presentazioni con interazioni minime da parte dei partecipanti, è possibile creare un modello che disattiva il video dei partecipanti e persino la chat e un altro modello che lascia tali opzioni all'organizzatore della riunione. Entrambi i modelli userebbero l'etichetta *Sensitive* .

Nel livello di protezione *sensibile* , useremo il modello per impedire alle persone che accedono tramite telefono di ignorare la sala d'attesa. Se ci sono determinati tipi di riunioni in cui si vuole consentire alle persone che chiamano telefonicamente di ignorare la sala di attesa, è consigliabile usare un modello separato con la stessa etichetta per le riunioni.

Per creare un modello di riunione personalizzato

1. Nell'interfaccia di amministrazione di Teams espandere **Riunioni** e selezionare **Modelli di riunione**.
1. Seleziona **Aggiungi**
1. Digitare un nome e una descrizione per il modello.
1. Nella sezione **Applica etichetta di riservatezza** scegliere l'etichetta creata sopra.
1. Seleziona **Applica etichetta di riservatezza** e quindi **seleziona Blocca**.
1. Assicurati che **Persone chiamata nel telefono possa ignorare la sala di attesa** sia impostata su **Disattivato**, quindi selezionala e seleziona **Blocca**.
1. Modificare eventuali impostazioni aggiuntive, se necessario.
1. Per impedire all'organizzatore della riunione di modificare un'impostazione, selezionarla e quindi selezionare **Blocca**.
1. Per impedire all'organizzatore della riunione di visualizzare un'impostazione, selezionarla e quindi scegliere **Nascondi**.
1. Selezionare **Salva**.

## <a name="related-topics"></a>Argomenti correlati

[Configurare le riunioni di Teams con tre livelli di protezione](configure-meetings-three-tiers-protection.md)

[Panoramica dei modelli di riunione personalizzati in Microsoft Teams](custom-meeting-templates-overview.md)

[Usare i modelli di riunione di Teams, le etichette di riservatezza e i criteri di amministrazione insieme per le riunioni riservate](meeting-templates-sensitivity-labels-policies.md)
