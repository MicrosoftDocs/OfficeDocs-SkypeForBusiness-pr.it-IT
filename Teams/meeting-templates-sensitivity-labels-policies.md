---
title: Usare i modelli di riunione di Teams, le etichette di riservatezza e i criteri di amministrazione insieme per le riunioni riservate
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
description: Informazioni su come usare i criteri di amministrazione di Teams insieme alle etichette di riservatezza e ai modelli di riunione per migliorare la sicurezza e la conformità per le riunioni sensibili.
ms.openlocfilehash: f0363a7e27df39da7270d9f492048b639f8a3d30
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800086"
---
# <a name="use-teams-meeting-templates-sensitivity-labels-and-admin-policies-together-for-sensitive-meetings"></a>Usare i modelli di riunione di Teams, le etichette di riservatezza e i criteri di amministrazione insieme per le riunioni riservate

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Nelle riunioni di Teams, gli organizzatori delle riunioni possono configurare [un'ampia gamma di impostazioni](https://support.microsoft.com/office/53261366-dbd5-45f9-aae9-a70e6354f88e) che determinano quali funzionalità sono disponibili nella riunione. Gli amministratori possono disabilitare o applicare valori specifici per queste impostazioni usando una combinazione di criteri di amministrazione, etichette di riservatezza e modelli di riunione.

[I modelli di riunione](custom-meeting-templates-overview.md) vengono creati e gestiti nell'interfaccia di amministrazione di Teams. Le etichette di riservatezza vengono create e recuperate nella Portale di conformità di Microsoft Purview. 

> [!Note]
> Le impostazioni delle riunioni nelle etichette di riservatezza e nei modelli di riunione personalizzati richiedono Teams Premium.

L'uso di criteri, modelli ed etichette di amministrazione insieme consente di rendere possibile un'ampia varietà di scenari di riunione per soddisfare le esigenze aziendali e di conformità per i diversi reparti dell'organizzazione.

## <a name="policies-labels-templates-and-meetings-settings"></a>Impostazioni di criteri, etichette, modelli e riunioni

La tabella seguente mostra un elenco delle funzionalità di Teams che possono essere utili per gestire le riunioni con esigenze di conformità diverse all'interno dell'organizzazione e dove possono essere configurate.

|Funzionalità|Criteri di amministrazione di Teams|Etichetta di riservatezza|Modello riunione|Organizzatore della riunione|
|:----|:----|:----|:----|:----|
|Consentire la fotocamera per i partecipanti|Le impostazioni dei criteri video e modalità IP per i video IP determinano quali partecipanti possono usare le loro fotocamere.|Nessuna impostazione|Può impedire o consentire la fotocamera per i partecipanti. È possibile applicare l'impostazione o consentire la modifica dell'organizzatore della riunione.|Può impedire o consentire la fotocamera per i partecipanti se non è bloccata da un modello.|
|Consentire il microfono per i partecipanti|L'impostazione Modalità per l'audio IP determina quali partecipanti possono usare i microfoni.|Nessuna impostazione|Può impedire o consentire il microfono per i partecipanti. È possibile applicare l'impostazione o consentire la modifica dell'organizzatore della riunione.|Può impedire o consentire il microfono per i partecipanti se non è bloccato da un modello.|
|Applicare una filigrana al feed video di tutti gli utenti|Può essere impostato su Attivato o Disattivato. Se impostato su Disattivato, non è disponibile nelle etichette di riservatezza, nei modelli di riunione o nelle impostazioni delle riunioni.|Può applicare o impedire filigrane nei feed video dei partecipanti o lasciare incontrollata l'impostazione.|È possibile applicare o impedire filigrane nei feed video dei partecipanti, a meno che l'impostazione non sia controllata da un'etichetta di riservatezza.|L'organizzatore della riunione può attivare o disattivare l'impostazione, a meno che l'impostazione non sia disabilitata dai criteri di amministrazione o applicata o disattivata da un modello di riunione o da un'etichetta di riservatezza.|
|Applicare una filigrana al contenuto condiviso|Può essere impostato su Attivato o Disattivato. Se impostato su Disattivato, non è disponibile nelle etichette di riservatezza, nei modelli di riunione o nelle impostazioni delle riunioni.|Può applicare o impedire filigrane sul contenuto condiviso sullo schermo o lasciare incontrollata l'impostazione.|Può applicare o impedire filigrane sul contenuto condiviso sullo schermo, a meno che l'impostazione non sia controllata da un'etichetta di riservatezza.|L'organizzatore della riunione può attivare o disattivare l'impostazione, a meno che l'impostazione non sia disabilitata dai criteri di amministrazione o applicata o disattivata da un modello di riunione o da un'etichetta di riservatezza.|
|Crittografia end-to-end|Quando è attivata, la crittografia end-to-end può essere attivata da un'etichetta di riservatezza, un modello di riunione o l'organizzatore della riunione.|Può applicare o impedire la crittografia end-to-end o lasciare l'impostazione non controllata.|Può applicare o impedire la crittografia end-to-end a meno che l'impostazione non sia controllata da un'etichetta di riservatezza.|L'organizzatore della riunione può attivare o disattivare l'impostazione, a meno che l'impostazione non sia disabilitata dai criteri di amministrazione o applicata o disattivata da un modello di riunione o da un'etichetta di riservatezza.|
|Gestire ciò che i partecipanti vedono|Nessuna impostazione|Nessuna impostazione|Può essere impostato su Attivato o Disattivato e può applicare l'impostazione o consentire all'organizzatore della riunione di modificarla.|L'organizzatore della riunione può attivare o disattivare l'impostazione, a meno che l'impostazione non sia attivata o disattivata da un modello di riunione.|
|Chat della riunione|Può essere impostato su Attivato, Disattivato o Attivato per tutti tranne i partecipanti anonimi. Se impostato su Disattivato, l'impostazione della chat viene disabilitata in etichette, modelli e impostazioni di riunione.|Può applicare la chat in modo che sia attiva, disattivata o solo riunione oppure lasciare incontrollata l'impostazione.|Se è abilitata nei criteri di amministrazione e non è controllata da un'etichetta di riservatezza, può essere impostata su Attivato, Disattivato o Solo riunione. È possibile applicare l'impostazione o consentire la modifica dell'organizzatore della riunione.|Se è abilitata dai criteri di amministrazione e non è applicata da un'etichetta di riservatezza o da un modello, il proprietario della riunione può impostare su Attivato, Disattivato o Solo riunione.|
|Persone chiamata in ingresso può ignorare la sala di attesa|Imposta l'impostazione predefinita per le nuove riunioni.|Se l'etichetta controlla chi può ignorare la sala di attesa, questa impostazione viene applicata attiva o disattivata, altrimenti non controllata.|Se non è controllato da un'etichetta di riservatezza, può essere impostato su Attivato o Disattivato. È possibile applicare l'impostazione o consentire la modifica dell'organizzatore della riunione.|Se non viene applicata da un'etichetta di riservatezza o da un modello, il proprietario della riunione può impostare su Attivato o Disattivato.|
|Impedire la copia del contenuto della chat negli Appunti|Nessuna impostazione|Può impedire la copia della chat della riunione. Non si applica ai partecipanti anonimi.|Nessuna impostazione|Nessuna impostazione|
|Registra automaticamente|Nessuna impostazione|Può applicare o impedire la registrazione automatica delle riunioni o essere lasciata non controllata.|Se non è controllato da un'etichetta di riservatezza, può essere impostato su Attivato o Disattivato e può applicare l'impostazione o consentire all'organizzatore della riunione di modificarla.|L'organizzatore della riunione può attivare o disattivare l'impostazione, a meno che l'impostazione non sia attivata o disattivata da un modello di riunione o da un'etichetta di riservatezza.|
|Chi può evitare la sala di attesa|Imposta l'impostazione predefinita per le nuove riunioni.|È possibile applicare una determinata opzione per gli utenti che possono ignorare la sala di attesa o possono essere lasciati incontrollati.|Se non è controllata da un'etichetta di riservatezza, seleziona un'impostazione per gli utenti che possono ignorare la sala di attesa. È possibile applicare l'impostazione o consentire la modifica dell'organizzatore della riunione.|L'organizzatore della riunione può scegliere chi può ignorare la sala di attesa, a meno che l'impostazione non sia applicata da un'etichetta o un modello.|
|Chi può presentare|Imposta l'impostazione predefinita per le nuove riunioni. I valori disponibili sono Organizzatori, Tutti nell'organizzazione e Tutti.|Può applicare le impostazioni di tutti, partecipanti autenticati, organizzatori o persone specifiche oppure può essere lasciato incontrollato.|Nessuna impostazione|L'organizzatore della riunione può selezionare chi può presentare, a meno che non sia applicato da un'etichetta di riservatezza.|
|Chi può registrare|Nessuna impostazione|Può applicare le impostazioni di organizzatori, organizzatori e relatori oppure può essere lasciato incontrollato.|Se non è controllata da un'etichetta di riservatezza, seleziona un'impostazione di organizzatori, organizzatori e relatori.  È possibile applicare l'impostazione o consentire la modifica dell'organizzatore della riunione.|L'organizzatore della riunione può scegliere chi può registrare, ovvero organizzatori, organizzatori e relatori, a meno che l'impostazione non sia applicata da un'etichetta o da un modello.|

## <a name="admin-policies-effect-on-sensitivity-labels-and-meeting-templates"></a>Effetto dei criteri di Amministrazione sulle etichette di riservatezza e sui modelli di riunione

Anche se alcuni criteri di amministrazione, ad esempio le impostazioni della sala di attesa e chi può presentare, specificano le impostazioni predefinite che l'organizzatore della riunione può modificare, la maggior parte dei criteri di amministrazione determina se una determinata caratteristica è disponibile per gli utenti.

Se una caratteristica non è disponibile per un determinato utente perché i criteri di amministrazione l'hanno disattivata, non può essere applicata da un'etichetta di riservatezza o da un modello di riunione.

Ad esempio, se si crea un'etichetta *altamente sensibile* e la si configura per applicare la filigrana e la crittografia end-to-end, l'applicazione verrà applicata solo se la filigrana e la crittografia end-to-end sono abilitate per l'organizzatore della riunione nei criteri di amministrazione.

Quando si pianificano i modelli di riunione e le etichette di riservatezza, assicurarsi che le impostazioni da controllare siano abilitate nei criteri di amministrazione, se necessario.

## <a name="sensitivity-labels-and-templates-together"></a>Etichette di riservatezza e modelli insieme

Alcune impostazioni sono disponibili solo nelle etichette di riservatezza, mentre altre sono disponibili solo nei modelli. Molti sono disponibili in entrambi:

- Chat
- Crittografia end-to-end
- Impostazioni della sala di attesa
- Registrazione di una riunione
- Watermarking

Ogni volta che si usa un'etichetta di riservatezza, le impostazioni configurate nell'etichetta hanno la precedenza su qualsiasi modello o impostazione dell'organizzatore della riunione.

Le impostazioni in un'etichetta di riservatezza possono essere lasciate incontrollate quando viene creata l'etichetta, consentendo a un modello o all'organizzatore della riunione di controllare queste impostazioni.

Le etichette di riservatezza vengono spesso usate per più scopi, etichettando documenti, siti, messaggi di posta elettronica e riunioni. È possibile evitare di creare etichette aggiuntive solo per le riunioni usando modelli insieme alle etichette per tenere conto delle varianti all'interno di un determinato tipo di riunione.

Ad esempio, il reparto marketing potrebbe avere requisiti diversi per le riunioni riservate rispetto al reparto ricerche. È possibile configurare le impostazioni comuni in un'etichetta di riservatezza e quindi rendere disponibili modelli separati per i due gruppi, in modo da perfezionare ulteriormente le impostazioni della riunione per il gruppo. Entrambi i modelli potrebbero usare la stessa etichetta.

## <a name="user-based-policies-and-meeting-based-policies"></a>Criteri basati su utenti e criteri basati su riunioni

I criteri di Teams, inclusi i criteri per le riunioni, vengono applicati a livello di utente o di gruppo. Le impostazioni dell'etichetta di riservatezza e del modello si applicano al singolo livello di riunione in cui vengono usati tali etichette e modelli. È consigliabile configurare le impostazioni nei criteri di amministrazione di Teams rispetto alle etichette o ai modelli di riservatezza.

Ecco alcuni esempi:

Se si vogliono impostazioni di sala di attesa predefinite diverse per il reparto ricerche e il reparto marketing, è possibile configurare queste impostazioni predefinite usando i criteri di amministrazione e modificarle ulteriormente con etichette o modelli.

Se si vuole che le filigrane siano disponibili solo per i responsabili della governance, è possibile abilitarle solo per gli utenti che usano criteri di amministrazione. È quindi possibile impostare etichette o modelli per l'applicazione delle filigrane, ma le filigrane verranno usate solo nelle riunioni organizzate dai funzionari della governance.

## <a name="different-meeting-types-with-the-same-sensitivity"></a>Tipi di riunione diversi con la stessa sensibilità

L'uso di modelli ed etichette insieme può essere utile se si hanno diversi tipi di riunioni con la stessa sensibilità. Ad esempio, se alcune riunioni sensibili sono interattive e altre sono presentazioni con un'interazione minima da parte dei partecipanti, è possibile creare due modelli:
- Uno che disattiva il video e l'audio dei partecipanti da usare per le presentazioni
- Uno che lascia il video e l'audio a discrezione dell'organizzatore della riunione da usare per le riunioni interattive

Entrambi i modelli potrebbero usare l'etichetta *Sensitive* , che consente di controllare impostazioni aggiuntive, ad esempio chi può ignorare la sala di attesa e chi può presentare.

## <a name="specify-default-values-that-meeting-organizers-can-change"></a>Specificare i valori predefiniti che gli organizzatori delle riunioni possono modificare

Anche se in genere le etichette applicano una determinata impostazione, i modelli possono applicare un'impostazione o consentire all'organizzatore della riunione di modificarla. In questo modo è possibile implementare impostazioni predefinite che soddisfano le proprie esigenze di conformità, offrendo agli organizzatori della riunione la possibilità di ignorare l'impostazione, se necessario.

Ad esempio, per un livello di protezione previsto, è possibile usare un'etichetta di riservatezza per disattivare le filigrane. Allo stesso tempo, è possibile usare un modello per impostare l'impostazione predefinita per gli utenti che possono evitare la sala di attesa, ma consentire all'organizzatore della riunione di modificare l'impostazione, se necessario.

È possibile assegnare l'etichetta di protezione prevista al modello in modo che vengano usati entrambi quando un organizzatore della riunione sceglie tale modello.

Alcuni criteri di amministrazione possono essere usati anche per impostare un valore predefinito che può essere modificato da un organizzatore della riunione. Tra questi vi sono i controlli della sala di attesa e chi può presentare.

## <a name="related-topics"></a>Argomenti correlati

[Panoramica dei modelli di riunione personalizzati in Microsoft Teams](custom-meeting-templates-overview.md)

[Configurare le riunioni di Teams con tre livelli di protezione](configure-meetings-three-tiers-protection.md)

[Usare le etichette di riservatezza per proteggere gli elementi del calendario, le riunioni e le chat di Teams](/microsoft-365/compliance/sensitivity-labels-meetings)
