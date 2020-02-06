---
title: Gestire le posizioni per i gateway ELIN in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: Decisioni necessarie per pianificare un database di informazioni sulla posizione o un database esterno simile per una distribuzione di E9-1-1 con i gateway ELIN, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 39e6c4170adc18687b284ec6f69a252c6efefab4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803036"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>Gestire le posizioni per i gateway ELIN in Skype for Business Server

Decisioni necessarie per pianificare un database di informazioni sulla posizione o un database esterno simile per una distribuzione di E9-1-1 con i gateway ELIN, in Skype for Business Server VoIP aziendale.

Per consentire a Skype for Business Server di specificare automaticamente le posizioni per i client all'interno di una rete, è necessario eseguire le attività seguenti:

- Compilare il database del servizio informazioni sulla posizione con un wiremap di rete e includere i numeri di identificazione della posizione di emergenza (ELINs) nel campo CompanyName.

- Pubblicare i percorsi in modo che siano disponibili per i client della rete.

- Caricare il numero ELINs nel database di identificazione automatica della posizione del vettore (PSTN) del gestore della rete telefonica pubblica.

Per informazioni dettagliate su come eseguire queste attività, vedere [configurare il database della posizione](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) nella documentazione relativa alla distribuzione.

> [!NOTE]
> I percorsi aggiunti al database della posizione centrale non sono disponibili per il client finché non sono stati pubblicati usando un comando di Skype for Business Server Management Shell e vengono replicati negli archivi locali del pool. Per informazioni dettagliate, vedere [pubblicazione del database della posizione](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) nella documentazione relativa alla distribuzione.

Questa sezione descrive le informazioni da considerare quando si prevede di aggiornare e gestire il database della posizione.

## <a name="planning-emergency-locations"></a>Pianificazione delle posizioni di emergenza

Quando si usano i gateway ELIN, si popola il database del servizio informazioni sulla posizione con l'indirizzo civico, una posizione specifica all'interno di un edificio e almeno un ELIN per ogni posizione. Durante la fase di pianificazione, è consigliabile decidere come assegnare un nome alle posizioni e come assegnarle.

### <a name="planning-location-names"></a>Pianificazione dei nomi delle posizioni

Il campo **percorso** del servizio informazioni posizione, che contiene la posizione specifica all'interno di un edificio, ha una lunghezza massima di 20 caratteri (inclusi gli spazi). In tale lunghezza limitata, provare a includere le operazioni seguenti:

- Un nome di facile comprensione che identifica la posizione del chiamante di 911 per evitare che i soccorritori di emergenza trovino la posizione specifica subito quando arrivano all'indirizzo civico. Questo nome di posizione può includere un numero di edificio, un numero di piano, un designatore alare, un numero di camera e così via. Evitare i soprannomi noti solo ai dipendenti, in modo che i soccorritori di emergenza possano accedere alla posizione errata.

- Un identificatore di posizione che consente agli utenti di vedere facilmente che il loro cliente ha rilevato la posizione corretta. Il client Skype for business concatena automaticamente e visualizza la **posizione** e i campi della **città** individuati nella relativa intestazione. Una buona procedura consiste nell'aggiungere l'indirizzo di strada dell'edificio a ogni identificatore di posizione, ad esempio "primo piano <street number>". Senza l'indirizzo stradale, un identificatore di posizione generico come "primo piano" può essere applicato a qualsiasi edificio della città.

- Se la posizione è approssimativa perché è determinata da un punto di accesso wireless, è consigliabile aggiungere la parola **[near]** , ad esempio "near 1 ° piano 1234".

### <a name="planning-elins"></a>Pianificazione di ELINs

Dopo aver deciso in che modo si vuole dividere lo spazio per l'edificio in posizioni, è necessario decidere il numero di ELIN da assegnare a ogni posizione. Ad esempio, in un edificio multipiano o multitenant, è possibile assegnare aree di emergenza diverse nell'edificio. In genere, ogni piano di un edificio viene designato come posizione. A ogni posizione viene quindi assegnato uno o più ELIN, che vengono usati come numeri di chiamata durante una chiamata di emergenza. Contattare il gestore PSTN per i numeri di telefono che è possibile usare per gli ELIN. La tabella seguente contiene un esempio di posizioni per un indirizzo di strada specifico.

**Posizione di esempio e assegnazioni ELIN**

|**Area edifici**|**Posizione**|**ELIN**|
|:-----|:-----|:-----|
|Primo piano  <br/> |1  <br/> |425-555-0100  <br/> |
|Secondo piano  <br/> |2  <br/> |425-555-0111  <br/> |
|Terzo piano  <br/> |3  <br/> |425-555-0123  <br/> |

I percorsi definiti devono soddisfare i requisiti seguenti:

- Rispettare le normative locali e nazionali/regionali in termini di area massima per località e numero di posizioni per indirizzo stradale.

- Sono sufficientemente specifici per facilitare l'individuazione del chiamante di emergenza.

## <a name="populating-the-location-database"></a>Popolamento del database della posizione

Le domande seguenti consentiranno di determinare come popolare il database della posizione.

 **Quale processo verrà usato per popolare il database della posizione?**

Dove sono i dati e quali sono i passaggi da eseguire per convertire i dati nel formato richiesto dal database della posizione? Si aggiungono percorsi singolarmente o in blocco usando un file CSV?

 **Si dispone di un database di terze parti che contiene già una mappatura delle posizioni?**

Usando l'opzione servizio informazioni posizione secondaria per connettersi a un database di terze parti, è possibile raggruppare e gestire le posizioni usando una piattaforma offline. Un vantaggio per questo approccio è che, oltre ad associare le posizioni agli identificatori di rete, è possibile associare le posizioni a un utente. Ciò significa che il servizio informazioni sulla posizione può restituire più indirizzi, provenienti dal servizio informazioni sulla posizione secondaria, a un client Skype for business. L'utente può quindi scegliere la posizione più appropriata.

Per l'integrazione con il servizio informazioni sulla posizione, il database di terze parti deve seguire lo schema di richiesta/risposta della posizione di Skype for Business Server. Per informazioni dettagliate, vedere [servizio Web per il protocollo di supporto E911](https://go.microsoft.com/fwlink/p/?linkid=213819). Per informazioni dettagliate sulla distribuzione di un servizio di informazioni sulla posizione secondaria, vedere [configurare un servizio di informazioni sulla posizione secondaria in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) nella documentazione relativa alla distribuzione.

Per informazioni dettagliate sulla compilazione del database della posizione, vedere [configurare il database della posizione](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) nella documentazione relativa alla distribuzione.

## <a name="maintaining-the-location-database"></a>Manutenzione del database della posizione

Dopo aver popolato il database della posizione, è necessario sviluppare una strategia per l'aggiornamento del database durante la modifica della configurazione della rete. Le domande seguenti consentono di determinare come gestire il database della posizione.

 **Come si aggiorna il database della posizione?**

Esistono diversi scenari che richiedono un aggiornamento al database della posizione, tra cui l'aggiunta di punti di accesso wireless (WAP), il ricablaggio di Office (con le diverse assegnazioni di switch) e l'espansione della subnet. Si aggiorna direttamente ogni singola posizione o si esegue un aggiornamento in blocco di tutte le posizioni usando un file CSV?

 **Si utilizzerà un'applicazione SNMP per corrispondere agli indirizzi MAC del client Skype for business alla porta e agli identificatori di switch?**

Se si usa un'applicazione SNMP, è necessario sviluppare un processo manuale che contenga la coerenza tra l'applicazione SNMP e il database della posizione e le informazioni sulla porta. Se l'applicazione SNMP restituisce un indirizzo IP dello chassis o un ID di porta non incluso nel database, il servizio informazioni sulla posizione non sarà in grado di restituire una posizione al client.


