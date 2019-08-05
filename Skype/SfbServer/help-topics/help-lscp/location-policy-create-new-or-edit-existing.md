---
title: Criteri di posizione creare nuovi o modifica esistenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
description: È possibile configurare i criteri percorso per determinare se il servizio Enhanced 9-1-1 (E9-1-1) è abilitato e come viene usato, nonché come vengono usate le informazioni sulla posizione per utenti e contatti.
ms.openlocfilehash: b0b1e16f7227100394dd132e52a17a3192ccab43
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194435"
---
# <a name="location-policy-create-new-or-edit-existing"></a>Criteri percorso: crearne di nuovi o modificare quelli esistenti

È possibile configurare i criteri percorso per determinare se il servizio Enhanced 9-1-1 (E9-1-1) è abilitato e come viene usato, nonché come vengono usate le informazioni sulla posizione per utenti e contatti.

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i campi presenti nella pagina.

- **Ambito** Identifica l'ambito dei criteri di posizione che si stanno creando o modificando: globale, sito o utente.

- **Nome** Ogni criterio di posizione richiede un nome. Ai criteri percorso globali e di sito viene assegnato un nome per impostazione predefinita e il nome non può essere modificato. Per i criteri percorso utente, usare un nome descrittivo che identifichi l'utente o il gruppo di utenti.

    > [!NOTE]
    > Questo nome non potrà essere modificato dopo aver salvato i criteri percorso.

- **Abilitare 9-1-1 avanzato (E9-1-1)** Selezionare questa casella di controllo per abilitare E9-1-1 per gli utenti a cui è stato assegnato il criterio di posizione.

- **Posizione** Specificare se vengono richieste informazioni sulla posizione agli utenti:

  - **Obbligatorio** Selezionare questa opzione se gli utenti devono ricevere informazioni sulla posizione quando il loro client viene registrato in una nuova posizione. Gli utenti possono ignorare la richiesta senza immettere le informazioni.

  - **Non necessario** Selezionare questa opzione se gli utenti non devono richiedere informazioni sulla posizione.

  - **Dichiarazione** di non responsabilità Selezionare questa opzione se gli utenti devono richiedere informazioni sulla posizione, ma verrà visualizzato un messaggio di non responsabilità se rifiutano la richiesta senza immettere le informazioni. Fino a quando le informazioni sulla posizione non vengono immesse, gli utenti possono fare solo chiamate di emergenza, ma non altri tipi di chiamate.

- **Usare la posizione per il E9-1-1 solo** Selezionare questa casella di controllo se le informazioni sulla posizione devono essere usate solo per le chiamate di emergenza.

- **Uso PSTN** Selezionare l'utilizzo PSTN (Public Switched Telephone Network) che verrà usato per determinare quale route vocale verrà usata per il routing delle chiamate di emergenza da client che usano questo profilo. La route associata a tale utilizzo deve puntare a un trunk SIP dedicato alle chiamate di emergenza o a un gateway ELIN (Emergency Location Identification Number) che instrada le chiamate di emergenza al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point) più vicino. Le opzioni sono **Interno**, **Locale** o **Chiamate interurbane**.

- **Numero di telefono E9-1-1** Specificare il numero composto per raggiungere i servizi di emergenza.

- **Maschera di chiamata E9-1-1** Specificare un numero che un utente compone, che viene quindi tradotto nel numero di chiamata di emergenza. Ad esempio, immettere un valore di 212 in questo campo in modo che un utente possa chiamare 212 per raggiungere i servizi di emergenza. In questo modo, i numeri di emergenza alternativi devono essere composti e i servizi di emergenza REACH (ad esempio, se qualcuno di un paese o di un'area geografica con un numero di emergenza diverso cerca di chiamare il numero del paese o dell'area geografica invece del numero paese o area geografica in cui si trovano attualmente. Puoi definire più maschere di chiamate di emergenza separando i valori con punti e virgola. Ad esempio, 212; 414. La lunghezza massima della stringa è di 100 caratteri. Ogni carattere deve essere una cifra da 0 a 9.

    > [!IMPORTANT]
    > Verificare che la maschera di composizione non corrisponda a un numero in un intervallo di numeri del parcheggio di chiamata, in quanto il routing del parcheggio di chiamata ha la precedenza sulla conversione della stringa di composizione di emergenza. Per visualizzare gli intervalli di numeri di parcheggio delle chiamate, fare clic su **funzionalità vocali** nella barra di spostamento sinistra e quindi su **chiama parcheggio**.

- **URI di notifica** Specificare uno o più URI SIP per ricevere una notifica quando viene eseguita una chiamata di emergenza. Ad esempio, digita l'URI SIP di Office Security della società per informare il personale della sicurezza con un messaggio istantaneo ogni volta che viene effettuata una chiamata di emergenza. Se la posizione del chiamante è disponibile, la posizione è inclusa nella notifica. Puoi specificare più URI SIP come elenco delimitato da virgole. Ad esempio, "SIP: security@litwareinc.com", "SIP: kmyer@litwareinc.com". La stringa deve essere da 1 a 256 caratteri di lunghezza e deve iniziare con il prefisso "SIP:". È anche possibile specificare le liste di distribuzione.

- **URI conferenza** Specificare l'URI SIP (in questo caso il numero di telefono) per consentire a una terza parte di partecipare alle chiamate di emergenza. Digitare, ad esempio, il numero di telefono dell'ufficio che si occupa della sicurezza aziendale per fare in modo che riceva una chiamata quando viene effettuata una chiamata di emergenza. L'impostazione di **Modalità conferenza** determina se la terza parte può partecipare alla chiamata o solo ascoltare. La stringa deve avere una lunghezza compresa tra 1 e 256 caratteri e deve iniziare con il prefisso sip:.

- **Modalità conferenza** Se è stato specificato un valore per l' **URI conferenza**, impostare questo campo su uno dei valori seguenti:

  - **Unidirezionale** Specifica che la terza parte può solo ascoltare la chiamata tra il chiamante e l'operatore PSAP.

  - **Due vie** Specifica che la terza parte può partecipare alla chiamata tra il chiamante e l'operatore PSAP.

Per informazioni dettagliate sulle funzionalità e le funzionalità del servizio di emergenza VoIP aziendale, vedere [Panoramica di E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso dei criteri percorso, vedere [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) nella documentazione relativa alle operazioni.


