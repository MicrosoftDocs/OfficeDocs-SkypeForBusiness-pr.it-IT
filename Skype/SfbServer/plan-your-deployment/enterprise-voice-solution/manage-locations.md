---
title: Gestire le posizioni per i provider di servizi trunk SIP in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: 'Decisioni necessarie per la pianificazione di un database delle informazioni sulla posizione o di un database esterno simile per una distribuzione E9-1-1 tramite provider di trunking SIP, in Skype for Business Server VoIP aziendale.'
---

# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Gestire le posizioni per i provider di servizi trunk SIP in Skype for Business Server

Decisioni necessarie per la pianificazione di un database delle informazioni sulla posizione o di un database esterno simile per una distribuzione E9-1-1 tramite provider di trunking SIP, in Skype for Business Server VoIP aziendale.

Per configurare Skype for Business Server per l'individuazione automatica dei client all'interno di una rete, è necessario popolare il database del servizio informazioni percorso con una wiremap di rete e pubblicare le posizioni oppure collegarsi a un database esterno che contiene già i mapping corretti. Come parte di questo processo, è necessario convalidare gli indirizzi civici delle posizioni con il provider di servizi E9-1-1. Per informazioni dettagliate, [vedere Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) nella documentazione relativa alla distribuzione.

Il database del servizio informazioni sulla posizione viene popolato con un ERL (Emergency Response Location), costituito da un indirizzo civico e dall'indirizzo specifico all'interno di un edificio. Il campo Posizione del servizio **informazioni** sulla posizione, che è la posizione specifica all'interno di un edificio, ha una lunghezza massima di 20 caratteri (spazi inclusi). Tentare di includere, in tale lunghezza, gli elementi seguenti:

- Un nome di facile comprensione che identifichi la posizione del chiamante del servizio di emergenza (911), per consentire agli addetti del servizio di emergenza di trovare immediatamente la posizione specifica quando si recano all'indirizzo. Questo nome di posizione può includere il numero di edificio, l'indicazione della scala, il numero del piano, il numero di porta e così via. Evitare nomi alternativi noti solo ai dipendenti, che potrebbero indirizzare gli addetti del servizio di emergenza nel posto sbagliato.

- Un identificatore di posizione che consente agli utenti di vedere facilmente che il Skype for Business ha selezionato la posizione corretta. Il Skype for Business client concatena automaticamente e visualizza i campi **Location** e **City** individuati nell'intestazione. È consigliabile aggiungere l'indirizzo dell'edificio a ogni identificatore di posizione, ad esempio "1° piano \<street number>". Se non viene specificato l'indirizzo, un identificatore di posizione generico come "1° piano" potrebbe riferirsi a qualsiasi edificio della città.

- Se la posizione è approssimativa perché è determinata da un punto di accesso wireless, è possibile aggiungere la parola **[Near]** (ad esempio, "Near 1st Floor 1234").

> [!NOTE]
> Le posizioni aggiunte al database delle posizioni centrali non sono disponibili per il client finché non vengono pubblicate tramite un comando di Skype for Business Server Management Shell e vengono replicate agli archivi locali del pool. Per informazioni dettagliate, vedere [Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database) nella documentazione relativa alla distribuzione.

Nelle sezioni seguenti vengono illustrate le considerazioni da tenere in considerazione durante la compilazione e la gestione del database delle località.

## <a name="populating-the-location-database"></a>Popolamento del database delle posizioni

Le domande seguenti consentono di determinare come popolare il database delle località.

 **Valutare quale processo verrà utilizzato per popolare il database delle posizioni.**

Esaminare dove si trovano i dati e quali operazioni è necessario eseguire per convertirli nel formato richiesto dal database delle posizioni. Considerare inoltre se le posizioni verranno aggiunte singolarmente o in gruppo tramite un file CSV.

 **Valutare se si dispone di un database di terze parti contenente già un mapping di posizioni.**

Utilizzando l'opzione Secondary Location Information service per connettersi a un database di terze parti, è possibile raggruppare e gestire le posizioni utilizzando una piattaforma offline. Uno dei vantaggi di questo approccio è che le posizioni possono essere associate non solo a identificatori di rete, ma anche a un utente. Ciò significa che il servizio informazioni percorso può restituire più indirizzi, provenienti dal servizio informazioni sulla posizione secondario, a un client Skype for Business secondario. L'utente può quindi scegliere la posizione più appropriata.

Per l'integrazione con il servizio informazioni percorso, il database di terze parti deve seguire lo schema di richiesta/risposta percorso di Lync Server. Per informazioni dettagliate,  [vedere "[MS-E911WS]: Web Service for E911 Support Protocol Specification"](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd). Per informazioni dettagliate sulla distribuzione di un servizio informazioni percorso secondario, vedere [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) nella documentazione relativa alla distribuzione.

Per informazioni dettagliate su come popolare il database delle posizioni, vedere [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) nella documentazione relativa alla distribuzione.

## <a name="maintaining-the-location-database"></a>Gestione del database delle posizioni

Dopo aver popolato il database delle posizioni, è necessario sviluppare una strategia per aggiornarlo in base alle modifiche di configurazione della rete. Le considerazioni seguenti possono essere utili per determinare come verrà gestito il database delle posizioni.

 **Valutare come verrà aggiornato il database delle posizioni.**

Esistono diversi scenari che richiedono un aggiornamento al database delle località, tra cui l'aggiunta di wap, il ricabling dell'ufficio (con assegnazioni di commutazione diverse) e l'espansione delle subnet. Considerare se si prevede di aggiornare direttamente ogni singola posizione o di eseguire un aggiornamento in blocco delle posizioni mediante un file CSV.

 **Considerare se verrà utilizzata un'applicazione SNMP per creare una corrispondenza tra gli indirizzi MAC dei client Lync e gli identificatori di porte e commutatori,**

Se si utilizza un'applicazione SNMP, è necessario sviluppare un processo manuale per mantenere la coerenza a livello di informazioni su porte e chassis dei commutatori tra l'applicazione SNMP e il database delle posizioni. Se l'applicazione SNMP restituisce un indirizzo IP dello chassis o un ID porta non incluso nel database, il servizio informazioni percorso non sarà in grado di restituire una posizione al client.