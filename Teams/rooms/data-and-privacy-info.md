---
title: Dati e informazioni sulla privacy
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 06/01/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Dati e informazioni sulla privacy
f1keywords: Microsoft Teams Rooms Managed Service Data and Privacy Information
ms.openlocfilehash: 5799288005a5d30152a6f810c0aa40d451198390
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270301"
---
# <a name="approach"></a>Approccio

I clienti che usano Microsoft Teams Rooms Servizi gestiti affidano a Microsoft le risorse più preziose, ovvero i dati. Si fidano che la sua privacy sarà protetta e che sarà utilizzata solo in un modo coerente con le loro aspettative.

La tecnologia segue i processi di privacy per assicurarsi che rispetti le promesse del cliente di raccogliere e usare i dati in modo efficace durante l'esecuzione del servizio.
## <a name="data-collection-and-privacy"></a>Raccolta dei dati e privacy

 Microsoft Teams Rooms Servizi gestiti monitora i dispositivi, raccoglie i dati dei contenuti dei clienti e accede e gestisce in remoto i dispositivi come amministratore. I dati raccolti sono limitati alle informazioni necessarie per monitorare l'integrità, la causa principale e i problemi di prevenzione identificati nelle chat room registrate. Alcuni dati raccolti sono specifici di un account della sala, non di singoli utenti.

> [!Note]
> Riferimenti accidentali a un singolo utente possono essere presenti nel log attività durante l'uso del dispositivo.

## <a name="who-can-access-data"></a>Chi può accedere ai dati

I servizi gestiti adottano misure efficaci per proteggere i dati dei clienti da accessi o utilizzi non appropriati da parte di persone non autorizzate. Tali misure includono la limitazione dell'accesso da parte di personale e subcontraenti Microsoft.

## <a name="zero-standing-access-data-storage"></a>Zero archiviazione dati di Accesso in piedi

I servizi gestiti riducono i rischi associati agli account con accesso privilegiato da parte di attori malintenzionati, sia all'interno che all'esterno di un'organizzazione, in base al principio di accesso permanente zero. Questo principio consente ai servizi gestiti di funzionare senza privilegi disponibili per qualsiasi utente per impostazione predefinita. In combinazione con i principi Just-In-Time e Just-Enough-Access, offre un framework affidabile per essere sicuro e conforme per impostazione predefinita. I dati di diagnostica sono disponibili per il team operativo del servizio Microsoft tramite un portale interno.

## <a name="data-handling"></a>Gestione dei dati

Microsoft è disciplinata da standard rigorosi per la trasmissione, l'archiviazione, l'uso e la conservazione dei dati. Microsoft ha definito criteri standard per la gestione dei dati che regolano la modalità di gestione dei dati in base alla classificazione dei dati.



## <a name="technology-description"></a>Descrizione della tecnologia

I servizi gestiti inviano dati a Microsoft allo scopo di monitorare, diagnosticare e attenuare eventuali problemi nella distribuzione. Gli esempi includono

- Verificare che il dispositivo sia aggiornato (inclusi l'app, il sistema operativo, i driver, F/W)
- Verificare che il dispositivo sia pronto per l'uso (accesso, tutte le periferiche che segnalano lo stato integro e così via)
- Verificare che l'ambiente sia pronto (account di cui è stato eseguito il provisioning, velocità di rete sufficientemente veloci e così via)
- Determinare se possono verificarsi problemi hardware o di installazione (ad esempio la disabilitazione allentata)
- Euristica per determinare i problemi (riavvii eccessivi e così via)

Servizi gestiti gestisce il dispositivo con le azioni seguenti:

- Aggiornare il software
- Riduci i problemi tramite riavvii, reimpostazione delle connessioni USB & stati
- Raccogliere log specifici per diagnosticare più facilmente i problemi

I servizi gestiti non monitorano né registrano contenuti audio, video, multimediali o delle riunioni dai kit di soluzioni.

### <a name="service-collected-data-categories"></a>Categorie di dati raccolti dal servizio
 
|Categoria|Dettagli|Motivo della query|
| :- | :- | :- |
|Raccolta e gestione dei dati in corso|Indirizzo IP, identità dell'account della chat room (Exchange, Skype for Business e/o Teams), coordinate della posizione, e-mail e comunicazione all'interno del portale con Microsoft o software|Identificare e connettersi al sistema in gestione; identificare, diagnosticare e mitigare i guasti; tenere traccia dell'utilizzo, dell'analisi e dei dati analitici; stato della connettività di query e ripristino|
|Raccolta e gestione dei dati ad hoc|Informazioni sul registro eventi, attività utente/identità dall'utente della chat room connesso al file di log insieme alle informazioni di diagnostica, query di sistema di Windows (esempi: elenco di dispositivi USB, stato di alimentazione e così via)|Identificare, diagnosticare e ridurre gli errori e per l'utilizzo, l'analisi e le informazioni dettagliate|

Alcuni dati sensibili nel log attività dispositivo vengono oscurati localmente (non raccolti dai servizi gestiti):

- Oggetto e corpo della riunione
- Informazioni sulla scheda contatto per i partecipanti alla riunione, ad esempio titolo, numero di telefono e così via.
- Contenuto del messaggio istantaneo della riunione

> [!NOTE]
> Man mano che Microsoft evolve i servizi gestiti, i dati specifici sono soggetti a modifica.

### <a name="enrollment"></a>Iscrizione

I servizi gestiti vengono registrati nel portale online per i servizi di supporto e monitoraggio automatizzati, inclusi i servizi di diagnostica e creazione di report. La registrazione viene eseguita tramite comunicazioni di rete crittografate tramite la chiave pubblica basata su TPM (Trusted Platform Module) del dispositivo.

### <a name="unenrollment"></a>Annullare la registrazione

È possibile annullare la registrazione del dispositivo disinstallando i servizi gestiti. Microsoft rimuove inoltre il dispositivo dal monitoraggio back-end durante la rimozione e può eliminare i dati raccolti su richiesta.
## <a name="compliance"></a>Conformità

Tutti i tecnici che lavorano sul prodotto sono tenuti a sottoporsi a formazione sulla sicurezza e sulla privacy. Microsoft garantisce inoltre che tutto il personale certifica l'accettazione delle responsabilità per i requisiti di privacy.

I servizi gestiti forniscono supporto regionale per la residenza dei dati tramite i data center in Europa (UE), Asia Pacifico (APAC) e Stati Uniti (Stati Uniti). I clienti del servizio avranno i dati relativi all'organizzazione archiviati nel data center dell'area geografica scelta.

## <a name="more-resources"></a>Altre risorse

Microsoft Teams Rooms Sicurezza:/microsoftteams/rooms/security Informativa sulla privacy di Microsoft: https://aka.ms/privacy Gestione dei dati presso Microsoft: https://www.microsoft.com/trust-center/privacy/data-management Descrizione del servizio Servizi gestiti: [Servizio gestito da sala di Microsoft Teams](microsoft-teams-rooms-premium.md)
