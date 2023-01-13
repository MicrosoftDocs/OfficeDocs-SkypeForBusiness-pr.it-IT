---
title: Configurare le riunioni di Teams con protezione per i dati altamente sensibili
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
description: Informazioni su come configurare le riunioni di Teams per la protezione di informazioni altamente riservate usando modelli ed etichette di riservatezza.
ms.openlocfilehash: 0d49cc4305f77b4b4208cc0f7418d5506155d0d6
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800263"
---
# <a name="configure-teams-meetings-with-protection-for-highly-sensitive-data"></a>Configurare le riunioni di Teams con protezione per i dati altamente sensibili

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Per il livello di protezione *altamente sensibile* , verranno descritti due diversi scenari:
- Riunioni altamente riservate in cui i partecipanti partecipano e interagiscono con i relatori
- Presentazioni altamente riservate in cui i partecipanti non interagiscono e visualizzano semplicemente la presentazione

> [!Note]
> Le impostazioni delle riunioni nelle etichette di riservatezza e nei modelli di riunione personalizzati richiedono Teams Premium.

#### <a name="highly-sensitive-meetings"></a>Riunioni altamente sensibili

Per le riunioni molto riservate, limiteremo gli utenti che possono evitare la sala di attesa, chi può presentare, quando i partecipanti possono chattare e bloccheremo la copia dalla chat della riunione. Abiliteremo anche la crittografia end-to-end e le filigrane per i video e i contenuti condivisi. Poiché le filigrane sono in uso, la registrazione delle riunioni verrà disabilitata.

La tabella seguente descrive le azioni che verranno limitate per le riunioni altamente riservate e la posizione in cui sono configurate tali impostazioni.

|Funzionalità|Impostazione|Posizione|Applicate|
|:------|:------|:-------|:-------|
|Consentire la fotocamera per i partecipanti|**Attivato**|Modello|No|
|Consentire il microfono per i partecipanti|**Attivato**|Modello|No|
|Applicare una filigrana al feed video di tutti gli utenti|**Attivato**|Etichetta|Sì|
|Applicare una filigrana al contenuto condiviso|**Attivato**|Etichetta|Sì|
|Crittografia end-to-end|**Attivato**|Etichetta|Sì|
|Gestire ciò che i partecipanti vedono|**Attivato**|Modello|Sì|
|Chat della riunione|**Solo in riunione**|Modello|Sì|
|Persone chiamata in ingresso può ignorare la sala di attesa|**Disattivato**|Etichetta|Sì|
|Impedire la copia del contenuto della chat negli Appunti|**Attivato**|Etichetta|Sì|
|Registra automaticamente|(Disabilitato a causa della filigrana e della crittografia)|N/D|N/D|
|Chi può evitare la sala di attesa|**Solo organizzatori e co-organizzatori**|Etichetta|Sì|
|Chi può presentare|**Solo organizzatori e co-organizzatori**|Etichetta|Sì|
|Chi può registrare|(Disabilitato a causa della filigrana e della crittografia)|N/D|N/D|

Le impostazioni elencate come applicate vengono applicate dall'etichetta di riservatezza o dal modello di riunione. Le impostazioni non applicate possono essere modificate dall'organizzatore della riunione.

#### <a name="highly-sensitive-presentations"></a>Presentazioni altamente sensibili

Per le presentazioni molto sensibili, in cui non ci si aspetta l'interazione con i partecipanti alla riunione, verranno disattivati microfoni e fotocamere dei partecipanti e la chat della riunione verrà disattivata.

Se si vuole consentire ai partecipanti di porre domande al relatore, gli organizzatori della riunione possono attivare la funzionalità Q&A. (Assicurarsi che sia abilitata nei criteri delle riunioni di amministrazione di Teams).

La tabella seguente descrive le azioni che verranno limitate per le presentazioni altamente riservate e la posizione in cui sono configurate queste impostazioni.

|Funzionalità|Impostazione|Posizione|Applicate|
|:------|:------|:-------|:-------|
|Consentire la fotocamera per i partecipanti|**Disattivato**|Modello|Sì|
|Consentire il microfono per i partecipanti|**Disattivato**|Modello|Sì|
|Applicare una filigrana al feed video di tutti gli utenti|**Attivato**|Etichetta|Sì|
|Applicare una filigrana al contenuto condiviso|**Attivato**|Etichetta|Sì|
|Crittografia end-to-end|**Attivato**|Etichetta|Sì|
|Gestire ciò che i partecipanti vedono|**Attivato**|Modello|Sì|
|Chat della riunione|**Disattivato**|Modello|Sì|
|Persone chiamata in ingresso può ignorare la sala di attesa|**Disattivato**|Etichetta|Sì|
|Impedire la copia del contenuto della chat negli Appunti|**Attivato**|Etichetta|Sì|
|Registra automaticamente|(Disabilitato a causa della filigrana e della crittografia)|N/D|N/D|
|Chi può evitare la sala di attesa|**Solo organizzatori e co-organizzatori**|Etichetta|Sì|
|Chi può presentare|**Solo organizzatori e co-organizzatori**|Etichetta|Sì|
|Chi può registrare|(Disabilitato a causa della filigrana e della crittografia)|N/D|N/D|

Le impostazioni elencate come applicate vengono applicate dall'etichetta di riservatezza o dal modello di riunione. Le impostazioni non applicate possono essere modificate dall'organizzatore della riunione.

## <a name="options-for-recording-meetings"></a>Opzioni per la registrazione di riunioni

Per il livello di protezione *molto sensibile* , usiamo le filigrane e la crittografia end-to-end sia per le riunioni che per le presentazioni. Tuttavia, l'uso di queste funzionalità impedisce la registrazione della riunione. Se è necessario registrare riunioni altamente riservate, è consigliabile non configurare filigrane e crittografia end-to-end come parte dell'etichetta di riservatezza. Possono comunque essere usati dagli organizzatori delle riunioni per le riunioni che non devono registrare.

## <a name="presentation-options-for-highly-sensitive-meetings"></a>Opzioni di presentazione per riunioni altamente riservate

Per le riunioni *altamente riservate* , stiamo applicando impostazioni specifiche per gli utenti che possono presentare e per la modalità di condivisione del contenuto.

Attivando **Gestisci ciò che i partecipanti possono vedere**, ci assicuriamo che gli organizzatori della riunione possano controllare i contenuti condivisi prima che vengano visualizzati sullo schermo per i partecipanti. In questo esempio viene usato un modello per attivare questa opzione per impostazione predefinita, ma è anche possibile applicarlo nel modello, se necessario.

Impostando **Chi può presentare** **solo gli organizzatori e i co-organizzatori** nell'etichetta di riservatezza, ci assicuriamo che le uniche persone che possono presentare siano quelle che intende l'organizzatore della riunione.

## <a name="lobby-options-for-sensitive-meetings"></a>Opzioni di sala di attesa per riunioni sensibili

Useremo l'etichetta di riservatezza per impedire a utenti diversi dagli organizzatori della riunione di ignorare la sala di attesa. In questo modo gli organizzatori possono controllare ogni partecipante e assicurarsi che siano ammessi.

## <a name="participation-options-for-highly-sensitive-meetings"></a>Opzioni di partecipazione per riunioni altamente riservate

Anche se la chat può essere controllata con l'etichetta di riservatezza, in questo caso useremo i modelli in modo che i modelli di riunione e presentazione possano condividere la stessa etichetta. La chat verrà limitata solo alle riunioni in corso e completamente disattivata per le presentazioni. Gli organizzatori possono usare la funzionalità Q&A nelle presentazioni per consentire commenti o domande al pubblico.

Sia per le riunioni che per le presentazioni, impediamo anche di copiare il contenuto della chat negli Appunti.

Anche se lasceremo il microfono e la fotocamera dei partecipanti abilitati per le riunioni, li disattiveremo per le presentazioni.

## <a name="sensitivity-labels"></a>Etichette di riservatezza

Per il livello di protezione dei dati sensibili, useremo un'etichetta di riservatezza che è possibile usare direttamente in una riunione o come parte di un modello di riunione. A seconda della configurazione scelta, questa etichetta può essere usata anche per classificare i team e i singoli file.

Se nell'organizzazione sono già state distribuite etichette di riservatezza, considerare come si adatta questa etichetta alla strategia generale per le etichette. Se necessario, è possibile modificare il nome o le impostazioni per soddisfare le esigenze dell'organizzazione. Se hai già un'etichetta che usi per informazioni riservate, puoi modificare l'etichetta e aggiungervi riunioni di Teams.

> [!IMPORTANT]
> Se un'etichetta di riservatezza che limita la copia dalla chat è specificata come etichetta di canale predefinita in un'etichetta contenitore, i team con quell'etichetta contenitore limiteranno la copia dalla chat per tutti i canali del team, sia all'interno che all'uscita dalle riunioni del canale.

Per creare un'etichetta di riservatezza
1. Aprire il [Portale di conformità di Microsoft Purview](https://compliance.microsoft.com).
1. In **Soluzioni** fare clic su **Protezione delle informazioni**.
1. Fare clic su **Crea un'etichetta**.
1. Assegnare un nome all'etichetta. È consigliabile scegliere **Altamente riservate**, ma è possibile scegliere un nome diverso se è già in uso.
1. Aggiungere un nome visualizzato e una descrizione e quindi fare clic su **Avanti**.
1. Nella pagina **Definire l'ambito per questa etichetta** selezionare **Elementi** e **Includi riunioni**. Se si vuole usare questa etichetta per altri scopi, è possibile selezionare altre opzioni.
1. Selezionare **Avanti**.
1. Continuare a selezionare le opzioni da usare con questa etichetta e quindi nella pagina **Impostazioni per le riunioni e le chat di Teams** scegliere i valori seguenti:
    1. Seleziona **Controlla chi può ignorare la sala di attesa** e seleziona **Solo organizzatori e co-organizzatori** dall'elenco a discesa.
    1. Assicurarsi che **l'opzione Consenti agli utenti con accesso aperto di ignorare la sala di attesa** sia deselezionata
    1. Seleziona **Controlla chi può presentare** e seleziona **Solo organizzatori e co-organizzatori** nell'elenco a discesa.
    1. Selezionare **Controlla crittografia end-to-end per il video e l'audio delle riunioni** e quindi impostare **Applica crittografia end-to-end** su **Attivato**.
    1. Selezionare **Controlla filigrane** e quindi impostare **Applica filigrana al contenuto condiviso** e **Applica filigrana al feed video di tutti** gli utenti su **Attivato**.
    1. Seleziona **Impedisci la copia del contenuto della chat negli Appunti**.
    1. Configurare le altre impostazioni necessarie per l'organizzazione.
    <!--:::image type="content" source="media/teams-meeting-sensitivity-label-highly-sensitive-small.png" alt-text="Screenshot of sensitivity label meeting settings." lightbox="media/teams-meeting-sensitivity-label-highly-sensitive-large.png":::-->
1. Selezionare **Avanti**.
1. Completa la procedura guidata con le impostazioni aggiuntive che vuoi usare, quindi seleziona **Crea etichetta** e quindi fai clic su **Fine**.

Dopo aver creato l'etichetta, è necessario pubblicarla agli utenti che la useranno. Per una protezione altamente sensibile, l'etichetta verrà reso disponibile a tutti gli utenti. L'etichetta viene pubblicata nel Portale di conformità di Microsoft Purview nella scheda **Criteri etichetta** della pagina **Protezione delle informazioni**. Se si ha un criterio esistente applicabile a tutti gli utenti, aggiungere questa etichetta a tale criterio. Se è necessario creare un nuovo criterio, vedere [Pubblicare etichette di riservatezza creando un criterio di etichetta](/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

Per altre informazioni sull'uso di etichette di riservatezza con le riunioni, vedere [Usare le etichette di riservatezza per proteggere gli elementi del calendario, le riunioni e le chat di Teams](/microsoft-365/compliance/sensitivity-labels-meetings).

## <a name="meeting-templates"></a>Modelli di riunione

Nel livello di protezione *molto sensibile* vengono configurate le impostazioni seguenti usando un modello di riunione:

- **Consentire la fotocamera per i partecipanti** -  **Attivato** ma non applicato per le riunioni e applicato **disattivato** per le presentazioni.
- **Consentire il microfono per i partecipanti** -  **Attivato** ma non applicato per le riunioni e applicato **disattivato** per le presentazioni.
- **Gestire ciò che i partecipanti possono vedere** **- Applicato sia** per le riunioni che per le presentazioni.
- **Chat riunione** : applicata solo alle riunioni in **riunione** e **disattivata** per le presentazioni.

Poiché queste impostazioni differiscono tra riunioni e presentazioni, creeremo un modello per ognuna delle quali condivide la stessa etichetta di riservatezza.

#### <a name="highly-sensitive-meetings-template"></a>Modello di riunioni altamente riservate

Per creare un modello di riunione per riunioni altamente riservate

1. Nell'interfaccia di amministrazione di Teams espandere **Riunioni** e selezionare **Modelli di riunione**.
1. Seleziona **Aggiungi**
1. Digitare un nome e una descrizione per il modello.
1. Nella sezione **Applica etichetta di riservatezza** scegliere l'etichetta creata sopra.
1. Seleziona **Applica etichetta di riservatezza** e quindi **seleziona Blocca**.
1. Imposta **Chat riunione** **su Solo in riunione** , quindi seleziona l'impostazione e seleziona **Blocca**.
1. Imposta **Gestisci i contenuti visualizzati dai partecipanti** **su Attivato** , quindi seleziona l'impostazione e seleziona **Blocca**.
1. Modificare eventuali impostazioni aggiuntive, se necessario.
1. Per impedire all'organizzatore della riunione di modificare un'impostazione, selezionarla e quindi selezionare **Blocca**.
1. Per impedire all'organizzatore della riunione di visualizzare un'impostazione, selezionarla e quindi scegliere **Nascondi**.
1. Selezionare **Salva**.

#### <a name="highly-sensitive-presentations-template"></a>Modello di presentazioni altamente riservate

Per creare un modello di riunione per presentazioni molto sensibili

1. Nell'interfaccia di amministrazione di Teams espandere **Riunioni** e selezionare **Modelli di riunione**.
1. Seleziona **Aggiungi**
1. Digitare un nome e una descrizione per il modello.
1. Nella sezione **Applica etichetta di riservatezza** scegliere l'etichetta creata sopra.
1. Seleziona **Applica etichetta di riservatezza** e quindi **seleziona Blocca**.
1. Imposta **Consenti microfono per i partecipanti** su **Attivato** , quindi seleziona l'impostazione e seleziona **Blocca**.
1. Imposta **Consenti fotocamera per i partecipanti** su **Attivato** , quindi seleziona l'impostazione e seleziona **Blocca**.
1. Imposta **Chat riunione** su **Disattivato** , quindi seleziona l'impostazione e seleziona **Blocca**.
1. Imposta **Gestisci i contenuti visualizzati dai partecipanti** **su Attivato** , quindi seleziona l'impostazione e seleziona **Blocca**.
1. Modificare eventuali impostazioni aggiuntive, se necessario.
1. Per impedire all'organizzatore della riunione di modificare un'impostazione, selezionarla e quindi selezionare **Blocca**.
1. Per impedire all'organizzatore della riunione di visualizzare un'impostazione, selezionarla e quindi scegliere **Nascondi**.
1. Selezionare **Salva**.

## <a name="related-topics"></a>Argomenti correlati

[Configurare le riunioni di Teams con tre livelli di protezione](configure-meetings-three-tiers-protection.md)

[Panoramica dei modelli di riunione personalizzati in Microsoft Teams](custom-meeting-templates-overview.md)

[Usare i modelli di riunione di Teams, le etichette di riservatezza e i criteri di amministrazione insieme per le riunioni riservate](meeting-templates-sensitivity-labels-policies.md)

[Usare le etichette di riservatezza per proteggere gli elementi del calendario, le riunioni e le chat di Teams](/microsoft-365/compliance/sensitivity-labels-meetings)
