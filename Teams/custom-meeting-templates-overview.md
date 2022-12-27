---
title: Panoramica dei modelli di riunione personalizzati in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ralphmaamari
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
appliesto:
- Microsoft Teams
description: Informazioni sui modelli di riunione personalizzati in Microsoft Teams Premium.
ms.openlocfilehash: 0ed766141e09b9c26d8e8c6f5e8fdd12195ddb78
ms.sourcegitcommit: 4fdbd93aacb52a4fca68e31eb04d0495d4e27a10
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/27/2022
ms.locfileid: "69672916"
---
# <a name="overview-of-custom-meeting-templates-in-microsoft-teams"></a>Panoramica dei modelli di riunione personalizzati in Microsoft Teams

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Microsoft Teams Premium include la possibilità di creare modelli di riunione personalizzati. I modelli di riunione possono essere usati per controllare le impostazioni che l'organizzatore della riunione controlla normalmente. Con i modelli è possibile creare esperienze di riunione coerenti nell'organizzazione e applicare i requisiti di conformità e le regole aziendali.

I modelli di riunione possono essere usati per applicare le impostazioni o per impostare le impostazioni predefinite. Ogni impostazione del modello può essere bloccata in modo che l'organizzatore della riunione non possa modificarla o può essere lasciata sbloccata per consentire all'organizzatore della riunione di modificarla, se necessario.

È possibile controllare le impostazioni seguenti usando un modello di riunione:

|Impostazione|Descrizione|
|:------|:----------|
|Chat|Specifica se la chat della riunione è disponibile. Può essere usato anche per impedire la chat prima e dopo la riunione.|
|Crittografia end-to-end|Specifica se la riunione è crittografata.|
|Lobby|Specifica chi può ignorare la sala di attesa e partecipare direttamente alla riunione.|
|Gestire ciò che i partecipanti vedono|Specifica se gli organizzatori della riunione possono visualizzare in anteprima e approvare il contenuto condiviso sullo schermo prima che gli altri partecipanti alla riunione possano vederlo.|
|Microfono e fotocamera per i partecipanti|Specifica se i partecipanti possono riattivare l'audio e usare la videocamera.|
|Inviare una notifica quando i chiamanti si uniscono e abbandonano|Specifica se viene riprodotto un suono quando le persone che chiamano tramite telefono accedono o abbandonano la riunione.|
|Q&A|Specifica se i partecipanti possono usare la caratteristica Q&A per porre domande durante la riunione.|
|Reazioni|Specifica se i partecipanti possono usare le reazioni o alzare la mano nella riunione.|
|Registrazione|Specifica chi può registrare e se la riunione viene registrata automaticamente.|
|Etichetta di riservatezza|Specifica l'etichetta di riservatezza da usare per la riunione.|
|Filigrane|Specifica se le filigrane vengono usate per i feed della fotocamera e il contenuto condiviso sullo schermo nella riunione.|

Ecco alcuni esempi di come può essere utile un modello:

- Applicazione della registrazione automatica delle riunioni per determinati tipi di riunioni.
- Limitare la chat e la fotocamera dei partecipanti e l'audio e usare la funzionalità Q&A per le riunioni in stile presentazione.
- Uso di un valore predefinito più rigoroso per gli utenti che possono evitare la sala di attesa, ma che consente all'organizzatore della riunione di modificare l'impostazione, se necessario.

Per informazioni su come creare modelli di riunione, vedere [Creare un modello di riunione personalizzato in Microsoft Teams](create-custom-meeting-template.md).

## <a name="templates-with-sensitivity-labels"></a>Modelli con etichette di riservatezza

I modelli hanno la possibilità di specificare un'etichetta di riservatezza. Le etichette possono anche essere applicate direttamente alle riunioni, indipendentemente da modelli. Le etichette di riservatezza possono controllare alcune delle stesse impostazioni dei modelli:

- Crittografia end-to-end
- Chat della riunione
- Registra automaticamente
- Chi può evitare la sala di attesa
- Chi può presentare
- Chi può registrare
- Filigrane

Se una di queste impostazioni è configurata nell'etichetta, queste impostazioni verranno ignorate nel modello.

## <a name="templates-included-with-teams"></a>Modelli inclusi in Teams

Teams Premium include diversi modelli di riunione predefiniti che è possibile rendere disponibili agli utenti:

- Riunione di grandi dimensioni
- Riunione protetta
- Municipio
- [Appuntamento virtuale](virtual-appointment-meeting-template.md)
- Webinar

Inoltre, questi modelli sono disponibili in Teams per l'istruzione:

- Classe
- Gruppo discussione
- Conferenza
- Conferenza genitori-insegnanti

Se necessario, è possibile aggiornare le impostazioni di questi modelli.

## <a name="related-topics"></a>Argomenti correlati

[Configurare le riunioni di Teams con tre livelli di protezione](configure-meetings-three-tiers-protection.md)

[Usare i modelli di riunione di Teams, le etichette di riservatezza e i criteri di amministrazione insieme](meeting-templates-sensitivity-labels-policies.md)
