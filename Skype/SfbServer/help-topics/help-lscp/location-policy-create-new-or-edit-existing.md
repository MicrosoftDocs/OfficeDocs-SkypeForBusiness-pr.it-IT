---
title: Criterio percorso creare nuovo o modificarne uno esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
description: È possibile configurare i criteri percorso per determinare se Enhanced 9-1-1 (E9-1-1) è abilitato e come viene usato, nonché come vengono utilizzate le informazioni sulla posizione per utenti e contatti.
ms.openlocfilehash: f171d841ec68b3e0b0b4f7c8b9d374ff2261d149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803966"
---
# <a name="location-policy-create-new-or-edit-existing"></a>Criteri percorso: crearne di nuovi o modificare quelli esistenti

È possibile configurare i criteri percorso per determinare se Enhanced 9-1-1 (E9-1-1) è abilitato e come viene usato, nonché come vengono utilizzate le informazioni sulla posizione per utenti e contatti.

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i campi presenti nella pagina.

- **Ambito** Identifica l'ambito del criterio percorso che si sta creando o modificando: globale, sito o utente.

- **Nome** Ogni criterio percorso richiede un nome. I criteri globali e percorso sito sono denominati per impostazione predefinita e il nome non può essere modificato. Per i criteri percorso utente, utilizzare un nome descrittivo che identifichi l'utente o il gruppo di utenti.

    > [!NOTE]
    > Dopo aver salvato il criterio percorso, non è possibile modificare il nome.

- **Abilitare Enhanced 9-1-1 (E9-1-1)** Selezionare questa casella di controllo per abilitare il servizio E9-1-1 per gli utenti a cui è stato assegnato il criterio percorso.

- **Posizione** Specificare se agli utenti vengono richieste le informazioni sulla posizione:

  - **Necessario** Selezionare questa opzione se agli utenti vengono richieste le informazioni sulla posizione quando il client esegue la registrazione in un nuovo percorso. Gli utenti possono ignorare la richiesta senza immettere le informazioni sulla posizione.

  - **Non richiesto** Selezionare questa opzione se agli utenti non vengono richieste le informazioni sulla posizione.

  - **Dichiarazione** di non responsabilità Selezionare questa opzione se agli utenti vengono richieste le informazioni sulla posizione, ma verrà visualizzato un messaggio di dichiarazione di non responsabilità se rifiutano la richiesta senza immettere le informazioni. Gli utenti possono completare una chiamata di emergenza, ma non altre chiamate fino a quando non immettono le informazioni sulla posizione.

- **Utilizzo del percorso solo per il servizio E9-1-1** Selezionare questa casella di controllo se le informazioni sulla posizione devono essere usate solo per le chiamate di emergenza.

- **Utilizzo PSTN** Selezionare l'utilizzo della rete PSTN (Public Switched Telephone Network) che verrà utilizzato per determinare quale route vocale verrà utilizzata per il routing delle chiamate di emergenza da client che utilizzano questo profilo. La route associata a tale utilizzo deve puntare a un trunk SIP dedicato alle chiamate di emergenza o a un gateway ELIN (Emergency Location Identification Number) che instrada le chiamate di emergenza al punto di raccolta PSAP più vicino. Le opzioni sono **Internal**, **local** o **Long Distance**.

- **Numero di chiamata E9-1-1** Specificare il numero che viene composto per raggiungere i servizi di emergenza.

- **Maschera di chiamata E9-1-1** Specificare un numero composto da un utente che viene quindi convertito nel numero di composizione di emergenza. Ad esempio, immettere un valore di 212 in questo campo in modo che un utente possa comporre 212 per raggiungere i servizi di emergenza. In questo modo è possibile comporre numeri di emergenza alternativi e continuare a chiamare i servizi di emergenza REACH (ad esempio, se un utente di un paese o un'area geografica con un numero di emergenza diverso cerca di comporre il numero del paese o dell'area geografica anziché il numero del paese o dell'area geografica in cui si trovano attualmente). È possibile definire più maschere di composizione del numero di emergenza separando i valori con un punto e virgola. Ad esempio, 212; 414. La lunghezza massima della stringa è di 100 caratteri. Ogni carattere deve essere costituito da una cifra compresa tra 0 e 9.

    > [!IMPORTANT]
    > Assicurarsi che la maschera di chiamata non sia la stessa di un numero in un intervallo di numeri di parcheggio, perché il routing del parcheggio di chiamata ha la precedenza sulla conversione della stringa di composizione di emergenza. Per visualizzare gli intervalli di numeri del parcheggio di chiamata, fare clic su **funzionalità vocali** sulla barra di spostamento sinistra, quindi fare clic su **parcheggio di chiamata**.

- **URI di notifica** Specificare uno o più URI SIP da notificare quando viene effettuata una chiamata di emergenza. Ad esempio, digitare l'URI SIP dell'ufficio di sicurezza aziendale per informare il personale della sicurezza con un messaggio istantaneo ogni volta che viene effettuata una chiamata di emergenza. Se la posizione del chiamante è disponibile, la posizione è inclusa nella notifica. È possibile specificare più URI SIP come elenco separato da virgole. Ad esempio, "SIP: security@litwareinc. com", "SIP: kmyer@litwareinc. com". La stringa deve avere una lunghezza da 1 a 256 caratteri e deve iniziare con il prefisso "SIP:". È inoltre possibile specificare le liste di distribuzione.

- **URI conferenza** Specificare l'URI SIP (in questo caso il numero di telefono) per una terza parte per la conferenza per le chiamate di emergenza. Ad esempio, digitare il numero di telefono dell'ufficio di sicurezza aziendale in modo che ricevano una chiamata quando viene effettuata una chiamata di emergenza. L'impostazione per la **modalità conferenza** determina se la terza parte può partecipare o semplicemente ascoltare la chiamata. La stringa deve avere una lunghezza compresa tra 1 e 256 caratteri e deve iniziare con il prefisso sip:.

- **Modalità conferenza** Se è stato specificato un valore per **URI conferenza**, impostare questo campo su uno dei valori seguenti:

  - **Unidirezionale** Specifica che la terza parte può solo ascoltare la chiamata tra il chiamante e l'operatore di PSAP.

  - **Two-Way** Specifica che la terza parte può partecipare alla chiamata tra il chiamante e l'operatore di PSAP.

Per informazioni dettagliate sulle funzionalità e sulle funzionalità del servizio di emergenza VoIP aziendale, vedere [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'utilizzo di criteri percorso, vedere [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) nella documentazione relativa alle operazioni.


