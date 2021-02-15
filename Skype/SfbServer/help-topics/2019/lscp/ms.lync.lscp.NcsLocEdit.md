---
title: Criteri percorso Crea nuovo o Modifica esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
ROBOTS: NOINDEX, NOFOLLOW
description: È possibile configurare i criteri percorso per determinare se enhanced 9-1-1 (E9-1-1) è abilitato e come viene usato, nonché come vengono utilizzate le informazioni sulla posizione per utenti e contatti.
ms.openlocfilehash: c1b1c21af9b0bee72e7b870f6252fdb118ee88d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836526"
---
# <a name="location-policy-create-new-or-edit-existing"></a>Criteri percorso: crearne di nuovi o modificare quelli esistenti

È possibile configurare i criteri percorso per determinare se enhanced 9-1-1 (E9-1-1) è abilitato e come viene usato, nonché come vengono utilizzate le informazioni sulla posizione per utenti e contatti.

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i campi presenti nella pagina.

- **Ambito** Identifica l'ambito del criterio percorso che si sta creando o modificando: globale, sito o utente.

- **Name** Ogni criterio percorso richiede un nome. I criteri percorso globale e sito sono denominati per impostazione predefinita e il nome non può essere modificato. Per i criteri percorso utente, utilizzare un nome descrittivo che identifichi l'utente o il gruppo di utenti.

    > [!NOTE]
    > Dopo aver salvato il criterio percorso, il nome non può essere modificato.

- **Abilitare enhanced 9-1-1 (E9-1-1)** Selezionare questa casella di controllo per abilitare E9-1-1 per gli utenti a cui è assegnato questo criterio percorso.

- **Posizione** Specificare se agli utenti vengono richieste informazioni sulla posizione:

  - **Obbligatorio** Selezionare questa opzione se agli utenti devono essere richieste informazioni sulla posizione quando il client esegue la registrazione in una nuova posizione. Gli utenti possono ignorare la richiesta senza immettere informazioni sulla posizione.

  - **Non obbligatorio** Selezionare questa opzione se agli utenti non vengono richieste informazioni sulla posizione.

  - **Dichiarazione di non responsabilità** Selezionare questa opzione se agli utenti devono essere richieste informazioni sulla posizione, ma verrà visualizzato un messaggio di dichiarazione di non responsabilità se rifiutano la richiesta senza immettere le informazioni. Gli utenti possono completare una chiamata di emergenza, ma non altre chiamate finché non immettono le informazioni sulla posizione.

- **Usare la posizione solo per il sistema E9-1-1** Selezionare questa casella di controllo se le informazioni sulla posizione devono essere utilizzate solo per le chiamate di emergenza.

- **Utilizzo PSTN** Selezionare l'utilizzo PSTN (Public Switched Telephone Network) che verrà utilizzato per determinare quale route vocale verrà utilizzata per il routing delle chiamate di emergenza dai client che utilizzano questo profilo. La route associata a tale utilizzo deve puntare a un trunk SIP dedicato alle chiamate di emergenza o a un gateway ELIN (Emergency Location Identification Number) che instrada le chiamate di emergenza al punto di raccolta PSAP più vicino. Le opzioni **sono Internal,** **Local** o **Long distance.**

- **Numero di composizione E9-1-1** Specificare il numero composto per raggiungere i servizi di emergenza.

- **Maschera di composizione E9-1-1** Specificare un numero composto da un utente, che viene quindi convertito nel numero di composizione per gli interventi di emergenza. Ad esempio, immettere il valore 212 in questo campo in modo che un utente possa comporre il 212 per raggiungere i servizi di emergenza. In questo modo è possibile comporre numeri di emergenza alternativi e fare in modo che la chiamata raggiunga comunque i servizi di emergenza (ad esempio, se un utente di un paese o di un'area geografica con un numero di emergenza diverso tenta di comporre il numero del paese o dell'area geografica in cui si trova attualmente). È possibile definire più maschere di composizione del numero di emergenza separando i valori con un punto e virgola. Ad esempio, 212;414. La lunghezza massima della stringa è 100 caratteri. Ogni carattere deve essere costituito da una cifra compresa tra 0 e 9.

    > [!IMPORTANT]
    > Assicurarsi che la maschera di composizione non sia uguale a un numero in un intervallo di numeri del parcheggio di chiamata, perché il routing del parcheggio di chiamata ha la precedenza sulla conversione delle stringhe di composizione di emergenza. Per visualizzare gli intervalli di numeri del parcheggio di chiamata, fare clic su **Funzionalità** vocali sulla barra di spostamento sinistra e quindi su **Parcheggio di chiamata.**

- **URI notifica** Specificare uno o più URI SIP da notificare quando viene effettuata una chiamata di emergenza. Ad esempio, digitare l'URI SIP dell'ufficio di sicurezza aziendale per inviare al personale di sicurezza un messaggio istantaneo ogni volta che viene effettuata una chiamata di emergenza. Se la posizione del chiamante è disponibile, la posizione viene inclusa nella notifica. È possibile specificare più URI SIP come elenco delimitato da virgole. Ad esempio, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". La stringa deve contenere da 1 a 256 caratteri e iniziare con il prefisso "sip:". È inoltre possibile specificare le liste di distribuzione.

- **URI conferenza** Specificare l'URI SIP (numero di telefono, in questo caso) di una terza parte per la conferenza alle chiamate di emergenza. Ad esempio, digitare il numero di telefono dell'ufficio di sicurezza aziendale in modo che ricevano una chiamata quando viene effettuata una chiamata di emergenza. L'impostazione **per la modalità conferenza** determina se la terza parte può partecipare o semplicemente ascoltare la chiamata. La stringa deve avere una lunghezza compresa tra 1 e 256 caratteri e deve iniziare con il prefisso sip:.

- **Modalità conferenza** Se è stato specificato un valore per **URI** conferenza, impostare questo campo su uno dei valori seguenti:

  - **Unidiresto** Specifica che la terza parte può solo ascoltare la chiamata tra il chiamante e l'operatore PSAP.

  - **Bidiredirei** Specifica che la terza parte può partecipare alla chiamata tra il chiamante e l'operatore PSAP.

Per informazioni dettagliate VoIP aziendale funzionalità e funzionalità del servizio di emergenza, vedere [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'utilizzo di criteri percorso, vedere [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) nella documentazione relativa alle operazioni.


