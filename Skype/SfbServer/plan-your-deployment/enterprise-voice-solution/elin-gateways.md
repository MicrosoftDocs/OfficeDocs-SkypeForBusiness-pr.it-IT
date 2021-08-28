---
title: Gestire le posizioni per i gateway ELIN in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: Decisioni necessarie per la pianificazione di un database delle informazioni sulla posizione o di un database esterno simile per una distribuzione E9-1-1 tramite gateway ELIN, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: bb0656909866a793bc8d64635b17785020dd646d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596506"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>Gestire le posizioni per i gateway ELIN in Skype for Business Server

Decisioni necessarie per la pianificazione di un database delle informazioni sulla posizione o di un database esterno simile per una distribuzione E9-1-1 tramite gateway ELIN, in Skype for Business Server VoIP aziendale.

Per fare Skype for Business Server automaticamente le posizioni dei client all'interno di una rete, è necessario eseguire le attività seguenti:

- Popolare il database del servizio informazioni percorso con una wiremap di rete e includere i numeri ELAN (Emergency Location Identification Numbers) nel campo CompanyName.

- Pubblicare le posizioni in modo che siamo disponibili per i client nella rete.

- Caricare i numeri ELIN nel database ALI (Automatic Location Identification) del gestore della rete PSTN (Public Switched Telephone Network).

Per informazioni dettagliate su come eseguire queste attività, vedere [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) nella documentazione relativa alla distribuzione.

> [!NOTE]
> I percorsi aggiunti al database delle posizioni centrale non sono disponibili per il client fino a quando non sono stati pubblicati utilizzando un comando di Skype for Business Server Management Shell e vengono replicati agli archivi locali del pool. Per informazioni dettagliate, vedere [Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database) nella documentazione relativa alla distribuzione.

In questa sezione vengono descritti gli aspetti da prendere in considerazione quando si pianificano l'aggiornamento e la gestione del database delle posizioni.

## <a name="planning-emergency-locations"></a>Pianificazione delle posizioni di emergenza

Quando si utilizzano gateway ELIN, si popola il database del servizio informazioni percorso con l'indirizzo civico, una posizione specifica all'interno di un edificio e almeno un ELIN per ogni posizione. Durante la fase di pianificazione, è opportuno decidere come denominare le posizioni e come assegnare i numeri ELIN.

### <a name="planning-location-names"></a>Pianificazione dei nomi delle posizioni

Il campo Posizione **del** servizio informazioni percorso, che contiene la posizione specifica all'interno di un edificio, ha una lunghezza massima di 20 caratteri (spazi inclusi). Tentare di includere gli elementi seguenti rispettando questi limiti di lunghezza:

- Un nome di facile comprensione che identifichi la posizione del chiamante del servizio di emergenza (911), per consentire agli addetti del servizio di emergenza di trovare immediatamente la posizione specifica quando si recano all'indirizzo civico. Questo nome di posizione può includere il numero di edificio, l'indicazione della scala, il numero del piano, il numero di porta e così via. Evitare nomi alternativi noti solo ai dipendenti, altrimenti si rischia che gli addetti del servizio di emergenza si rechino nel luogo sbagliato.

- Identificatore di posizione che consente agli utenti di vedere facilmente che il client ha selezionato la posizione corretta. Il Skype for Business client concatena automaticamente e visualizza i campi **Location** e **City** individuati nell'intestazione. È consigliabile aggiungere l'indirizzo dell'edificio a ogni identificatore di posizione, ad esempio "1° piano <street number> ". Se non viene specificato l'indirizzo, un identificatore di posizione generico come "1° piano" potrebbe riferirsi a qualsiasi edificio della città.

- Se la posizione è approssimativa perché è determinata da un punto di accesso wireless, è possibile aggiungere la parola **[Near]** (ad esempio, "Near 1st Floor 1234").

### <a name="planning-elins"></a>Pianificazione dei numeri ELIN

Dopo aver stabilito come suddividere lo spazio dell'edificio in posizioni, è necessario decidere quanti numeri ELIN assegnare a ogni posizione. In un edificio a più piani o con più occupanti ad esempio è possibile assegnare alle diverse aree dell'edificio diverse zone di emergenza. In genere, ogni piano di un edificio viene designato come posizione. A ogni posizione vengono quindi assegnati uno o più numeri ELIN, utilizzati come numeri chiamanti durante una chiamata di emergenza. Contattare il gestore PSTN per conoscere i numeri di telefono che è possibile utilizzare come numeri ELIN. Nella tabella seguente sono illustrati alcuni esempi di posizioni per un indirizzo specifico.

**Posizioni e assegnazioni di numeri ELIN di esempio**

|**Area dell'edificio**|**Posizione**|**ELIN**|
|:-----|:-----|:-----|
|Primo piano  <br/> |1   <br/> |425-555-0100  <br/> |
|Secondo piano  <br/> |2   <br/> |425-555-0111  <br/> |
|Terzo piano  <br/> |3   <br/> |425-555-0123  <br/> |

Le posizioni definite devono soddisfare i requisiti seguenti:

- Essere conformi alle disposizioni locali e nazionali/regionali in termini di area massima per posizione e numero di posizioni per indirizzo.

- Essere sufficientemente specifiche da consentire di individuare senza difficoltà la persona che effettua la chiamata di emergenza.

## <a name="populating-the-location-database"></a>Popolamento del database delle posizioni

Le considerazioni seguenti possono essere utili per determinare come verrà popolato il database delle posizioni.

 **Valutare quale processo verrà utilizzato per popolare il database delle posizioni.**

Esaminare dove si trovano i dati e quali operazioni è necessario eseguire per convertirli nel formato richiesto dal database delle posizioni. Considerare inoltre se le posizioni verranno aggiunte singolarmente o in gruppo tramite un file CSV.

 **Valutare se si dispone di un database di terze parti contenente già un mapping di posizioni.**

Utilizzando l'opzione Secondary Location Information service per connettersi a un database di terze parti, è possibile raggruppare e gestire le posizioni utilizzando una piattaforma offline. Uno dei vantaggi di questo approccio è che le posizioni possono essere associate non solo a identificatori di rete, ma anche a un utente. Ciò significa che il servizio informazioni sulla posizione può restituire più indirizzi, provenienti dal servizio informazioni sulla posizione secondario, a un client Skype for Business secondario. L'utente può quindi scegliere la posizione più appropriata.

Per l'integrazione con il servizio informazioni percorso, il database di terze parti deve seguire lo schema di richiesta/risposta Skype for Business Server percorso. Per informazioni dettagliate, vedere [Web Service for E911 Support Protocol](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd). Per informazioni dettagliate sulla distribuzione di un servizio informazioni percorso secondario, vedere [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) nella documentazione relativa alla distribuzione.

Per informazioni dettagliate su come popolare il database delle posizioni, vedere [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) nella documentazione relativa alla distribuzione.

## <a name="maintaining-the-location-database"></a>Gestione del database delle posizioni

Dopo aver popolato il database delle posizioni, è necessario sviluppare una strategia per aggiornarlo in base alle modifiche di configurazione della rete. Le considerazioni seguenti possono essere utili per determinare come verrà gestito il database delle posizioni.

 **Valutare come verrà aggiornato il database delle posizioni.**

Esistono diversi scenari che richiedono un aggiornamento del database delle posizioni, tra cui l'aggiunta di punti di accesso wireless, il ricablaggio degli uffici (con assegnazioni diverse dei commutatori) e l'espansione delle subnet. Considerare se si prevede di aggiornare direttamente ogni singola posizione o di eseguire un aggiornamento in blocco delle posizioni mediante un file CSV.

 **Si userà un'applicazione SNMP per associare Skype for Business indirizzi MAC client agli identificatori di porta e commutatore?**

Se si utilizza un'applicazione SNMP, è necessario sviluppare un processo manuale per mantenere la coerenza a livello di informazioni su porte e chassis dei commutatori tra l'applicazione SNMP e il database delle posizioni. Se l'applicazione SNMP restituisce un indirizzo IP dello chassis o un ID porta non incluso nel database, il servizio informazioni percorso non sarà in grado di restituire una posizione al client.