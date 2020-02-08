---
title: Elenco di controllo onboarding per la configurazione della rete per Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Seguire le attività di base di questo elenco di controllo quando si configura la rete per i team.
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97a59ede284474069f39dc166d77d0a4a6ebc167
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862886"
---
# <a name="configure-networking"></a>Configurare la rete

| No | Attività o attività | Descrizione | Completato? | Altre informazioni |
|----|--------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Rivedere i requisiti di rete per i team | Avere una visione complessiva dei requisiti di rete prima di passare ai dettagli di rete. | | [Preparare la rete dell'organizzazione per Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network)                                                               |
| 2  | Distribuire il workshop di conformità della rete | Eseguire una valutazione della conformità della rete. | |  |
| 3  | Usare Network Planner | Eseguire la pianificazione della larghezza di banda della rete. | | |
| 4  | Convalidare le dimensioni del pool NAT necessarie per la connettività degli utenti | Verificare che gli indirizzi IP pubblici adeguati vengano assegnati ai pool NAT per evitare l'esaurimento della porta. L'esaurimento della porta contribuirà agli utenti e ai dispositivi interni non essendo in grado di connettersi al servizio Office 365. <br/><br/>I problemi di connettività sono una delle cause principali dei problemi di percezione degli utenti per i servizi cloud. | | [Supporto NAT con Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9) |
| 5  | Implementare il routing più efficiente per i datacenter Microsoft | Identificare le posizioni che possono usare i punti di uscita locali o regionali per connettersi alla rete Microsoft nel modo più efficiente possibile. <br/><br/>L'articolo della colonna **informazioni aggiuntive** descrive in che modo i client possono sfruttare le funzionalità della risoluzione dei nomi di Office 365 e del routing IP per essere connessi efficacemente al Data Center regionale più vicino. | | [Connettività client di Office 365](https://support.office.com/article/Client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b) |
| 6  | Configurare le porte del firewall richieste per la connettività ai team | Esaminare gli URL e gli indirizzi IP di Office 365 per identificare e testare le porte del firewall necessarie per la connettività tra client e server locali e i servizi di Office 365. <br/><br/>Per un ambiente supportato, è necessario aprire tutte le porte nei firewall. La mancata apertura di alcune porte o intervalli influirà negativamente sull'esperienza utente. Configurare le porte multimediali sui firewall in base alle indicazioni della colonna **informazioni aggiuntive** . | | [URL e indirizzi IP di Office 365-Microsoft Teams](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) |
| 7  | Configurare i server proxy | Configurare l'ambiente in modo che i server proxy vengano ignorati ed è possibile connettere gli utenti direttamente a Office 365 tramite UDP per ottenere la migliore qualità audio e video. Quando l'elemento multimediale in tempo reale viene costretto a attraversare un server proxy, lo stack multimediale in teams viene costretto a non eseguire più il failback su TCP, che influisce negativamente sulla qualità. <br/><br/>Per l'esperienza utente di qualità superiore, preferisca sempre UDP su TCP. | | [Pianificazione per la gestione e la qualità dei servizi](https://docs.microsoft.com/MicrosoftTeams/prepare-network) |
| 8  | Configurare la VPN con tunnel suddivisi | Ti consigliamo di specificare un percorso alternativo per il traffico di team che bypassa la VPN, comunemente nota come *VPN a tunnel suddiviso*. Suddividi tunneling significa che il traffico per Office 365 non percorre la VPN ma passa direttamente a Office 365. Questa modifica avrà un impatto positivo sulla qualità, ma offre anche il vantaggio secondario di ridurre il carico dai dispositivi VPN e dalla rete dell'organizzazione. | | Per implementare una VPN con tunnel suddiviso, consulta il fornitore di VPN per informazioni dettagliate sulla configurazione. |
| 9  | Configurare la priorità dei pacchetti tramite QoS | La QoS deve essere implementata in tutti i segmenti di una rete gestita. Anche quando una rete è stata adeguatamente provisionata per la larghezza di banda, QoS offre soluzioni di prevenzione dei rischi in caso di eventi di rete non previsti. Quando viene implementato il QoS, il traffico vocale viene assegnato in modo che questi eventi imprevisti non incidano negativamente sulla qualità. | | [Pianificazione per la gestione e la qualità dei servizi](https://docs.microsoft.com/MicrosoftTeams/prepare-network) <br/><br/>[Qualità del servizio in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams) |
| 10 | Ottimizzare le reti Wi-Fi per qualità e prestazioni | Quando si ottimizza la rete Wi-Fi, entrano in gioco diversi fattori: <ul><li>Implementazione di QoS o Wi-Fi Multimedia (WMM) per garantire che il traffico multimediale sulle reti Wi-Fi sia prioritario.</li><li>Pianificare e ottimizzare le bande Wi-Fi e la posizione del punto di accesso. L'intervallo di 2,4 GHz può consentire prestazioni adeguate, a seconda della posizione del punto di accesso.</li></ul> Consultare il fornitore Wi-Fi per indicazioni specifiche. | | [Raccomandazioni Wi-Fi per gli endpoint](https://docs.microsoft.com/MicrosoftTeams/prepare-network#wi-fi-recommendations-for-endpoints) |
| 11 | Convalidare la connettività di rete usando lo strumento di valutazione della rete | USA lo strumento di valutazione della rete per Skype for business e teams per testare la connettività a tutti gli indirizzi IP e alle porte usate in Skype for business online e le chiamate e le riunioni di teams. Scaricare lo strumento e vedere Usage. docx per informazioni dettagliate su come usare lo strumento e interpretare i risultati del test. È consigliabile eseguire lo strumento da un PC client in ogni posizione in cui verranno usati i team. | | [Strumento di valutazione della rete di Skype for business e teams](https://go.microsoft.com/fwlink/?linkid=855799) |
