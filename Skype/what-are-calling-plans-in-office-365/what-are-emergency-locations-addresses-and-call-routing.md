---
title: Che cosa sono il routing delle chiamate, gli indirizzi e le posizioni per gli interventi di emergenza?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: b6f9ffcbba68a7892a137a68565de97fe390d00f
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>Che cosa sono il routing delle chiamate, gli indirizzi e le posizioni per gli interventi di emergenza?

Quando si configura la chiamata dei piani in Office 365, è necessario che un indirizzo di emergenza essere assegnato a ogni numero di telefono è uno ottenere il numero di telefono o quando il relativo assegnati a un utente per il supporto di chiamate di emergenza. Prima di assegnare un indirizzo di emergenza a un numero di telefono, è necessario creare un indirizzo di emergenza e convalidato. La convalida garantisce che l'indirizzo di emergenza viene riconosciuta e che sia in un formato corretto che può essere utilizzato dai servizi di emergenza. Facoltativamente, una posizione all'interno dell'indirizzo emergenza è possibile aggiungere per fornire una posizione più specifica per l'utente. Ad esempio, il percorso di emergenza potrebbe essere un floor, ala o office collegato a un indirizzo specifico di emergenza. Anche se viene convalidato l'indirizzo di emergenza, non sono le posizioni.
  
## <a name="what-are-emergency-addresses"></a>Che cosa sono gli indirizzi per gli interventi di emergenza?

Un indirizzo di emergenza è necessario per i numeri telefonici attivo, ma quando è necessario che dipende il paese/area geografica. Negli Stati Uniti, è **necessario** un indirizzo emergenza quando viene assegnato un numero a un utente. Per altri paesi, ad esempio in Europa, Medio Oriente e Africa (EMEA), un indirizzo di emergenza è **necessario** quando si ottiene il numero di telefono da Office 365 oppure quando viene trasferita da un altro provider di servizi o gestore di telefonia.
  
Un indirizzo di emergenza può essere definito un indirizzo civico, numero civico o un indirizzo fisico. È l'indirizzo civico o civico di una sede di attività per l'organizzazione. Ad esempio, l'indirizzo *che 12345 Nord Main Street., Redmond, WA 98052* viene utilizzata per instradare le chiamate di emergenza per le autorità intervento appropriato e facilitano l'individuazione al chiamante di emergenza. È probabile che saranno necessari più di un indirizzo di emergenza se l'azienda dispone di più di una posizione fisica business.
  
Convalida un indirizzo di emergenza implica assicurandosi che sia valido e formattato in modo corretto per i servizi di emergenza. È possibile creare e salvare un indirizzo di emergenza che non viene convalidato, ma solo gli indirizzi convalidati possono essere associati a un utente. Dopo avere un indirizzo di emergenza viene convalidato e salvato, possono essere assegnato a un utente. Se si desidera modificare un indirizzo di emergenza convalidato salvato, sarà necessario crearne uno nuovo.
  
## <a name="what-are-emergency-locations"></a>Che cosa sono le posizioni per gli interventi di emergenza?

Posizioni di emergenza sono associate a un indirizzo di emergenza per fornire una posizione più preciso all'interno di un edificio. Un percorso di emergenza è in genere un piano, ala edificio o numero dell'ufficio in cui si trova l'utente. È possibile avere un numero illimitato di posizioni associate a un indirizzo di emergenza. 
  
Quando si assegna un utente un indirizzo di emergenza, è effettivamente un ID di posizione viene fatto riferimento quando si assegna l'indirizzo. ID posizione include l'indirizzo di emergenza riferimento (l'indirizzo civico o civico). Posizione predefinita del emergenza è inclusa in un indirizzo per il caso di emergenza quando non sono necessari i percorsi di creazione. 
  
## <a name="what-is-emergency-call-routing"></a>Che cos'è il routing delle chiamate di emergenza?

Percorsi e gli indirizzi di emergenza vengono utilizzati durante il processo di routing delle chiamate di emergenza al centro di intervento appropriato in fase di invio operatori prima. Quando un Skype per gli utenti aziendali componga un numero di emergenza, come la chiamata viene indirizzata a esecuzione Public Safety nazionale (PSAP) variano in base paese/area geografica. In alcuni paesi, ad esempio Stati Uniti e Regno Unito, le chiamate verranno essere preliminarmente per determinare la posizione corrente dell'utente prima di connettere la chiamata al centro di intervento appropriato. In altri paesi, le chiamate vengono instradate direttamente al centro di spedizione gestiscono il numero di telefono associato al chiamante di emergenza.
  
## <a name="creating-adding-and-assigning-emergency-locations-and-addresses-to-your-users"></a>Creazione, aggiunta e l'assegnazione di posizioni di emergenza e indirizzi per gli utenti

1. **Pianificare posizioni di emergenza** Il primo passaggio consiste nel pianificare per le posizioni di emergenza. È necessario ottenere un elenco di tutti gli indirizzi fisici. Quindi, in base a ciò, determinare se sono necessari i percorsi per gli indirizzi di emergenza e, in caso affermativo, quali. Ad esempio, se un'azienda ha 3 office edifici ogni con 4 piani, è probabile che devono essere 3 indirizzi di emergenza, con piani elencato come percorso per ognuna da 1 a 4.
    
2. **Crea e convalidare le posizioni di emergenza** Il passaggio successivo consiste nel creare e convalidare gli indirizzi di emergenza. Quando si crea un indirizzo di emergenza, è possibile convalidarlo. Per creare un indirizzo di emergenza, vedere [aggiungere o rimuovere un'emergenza indirizzo per l'organizzazione](add-or-remove-an-emergency-address-for-your-organization.md).
    
    > [!IMPORTANT]
    > Convalida un indirizzo civico o civico comporta assicurandosi che sia valido e formattato in modo corretto. È possibile che un indirizzo di emergenza parzialmente corretto, ad esempio il nome della città, errato può passare ancora passaggio di convalida. Il processo di convalida utilizza tutte le parti di un indirizzo specifico per determinare se contiene le informazioni necessarie per instradare la chiamata al centro di intervento di emergenza appropriato. In tal caso, verranno restituito come convalidata e possono essere quindi assegnata a un numero di telefono. 
  
3. **Ottenere numeri di telefono** Il passaggio successivo consiste nell'eseguire i numeri di telefono per gli utenti. Per farlo recuperando nuovi numeri di telefono da Office 365 o da "porting" o il trasferimento di numeri di telefono esistente su a Office 365. Per le procedure complete, vedere [trasferire i numeri di telefono a Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Assegnare i numeri di telefono** L'ultimo passaggio consiste nel consentire agli utenti di effettuare e ricevere chiamate telefoniche. A tale scopo, è necessario assegnare un numero di telefono per ogni utente. Vedere [assegnare, modificare o rimuovere un numero di telefono di un utente](assign-change-or-remove-a-phone-number-for-a-user.md) a cui assegnare un numero di telefono.

> [!NOTE]
> Se si desidera ottenere altri numeri di telefono rispetto a quella, [contattare il supporto per i prodotti di business - della Guida di amministrazione](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

    
## <a name="related-topics"></a>Argomenti correlati
[Che cos'è la convalida dell'indirizzo?](what-is-address-validation.md)

[Diversi tipi di numeri di telefono utilizzati per la chiamata dei piani](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Termini e condizioni per le chiamate al numero di emergenza](../what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions.md)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://go.microsoft.com/fwlink/?LinkID=692099)
