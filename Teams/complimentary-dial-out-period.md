---
title: Periodo di accesso gratuito
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, OscarR
ms.topic: conceptual
ms.assetid: dc6e95cd-51e8-49ca-bcd3-78dc9dae486a
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: None
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
description: Informazioni sul periodo di chiamata in uscita gratuito per Microsoft 365 piano chiamate Office 365 chiamate e Office 365 audioconferenza in Microsoft Teams.
ms.openlocfilehash: bf82b9ffc24000244a2666dedf2bb3ff8cd280cb476d6550747807411a4b9475
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347390"
---
# <a name="audio-conferencing-complimentary-dial-out-period"></a>Periodo di chiamate gratuite di Audioconferenza

## <a name="skype-for-business-pstn-services"></a>Servizi di conferenza PSTN Skype for Business

I clienti possono usare Microsoft 365 o Office 365 piano chiamate e audioconferenza Office 365 come consentito nelle Condizioni d'uso dei servizi PSTN online di Skype for Business e nel contratto multilicenza del cliente. Le condizioni di utilizzo dei servizi PSTN sono disponibili all'indirizzo [Condizioni e documentazione della licenza](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=2&amp;Keyword=PSTN).
  
### <a name="end-of-complimentary-dial-out-period"></a>Fine del periodo di chiamata in uscita gratuito

La funzionalità di chiamata in uscita gratuita è terminata il 1° dicembre 2019. Per altre informazioni, vedere Chiamata in uscita dell'abbonamento ai servizi di audioconferenza [e chiamami a vantaggio.](audio-conferencing-subscription-dial-out.md) 

Questa modifica non è stata apportata per i paesi in cui è disponibile l'abbonamento ai servizi di audioconferenza, ma attualmente non è possibile configurare i Crediti comunicazioni. Questi paesi specifici sono Russia, Corea del Sud e Taiwan.

### <a name="complimentary-dial-out-period-details"></a>Dettagli del periodo di chiamata in uscita gratuito

Per i clienti che adottano il servizio di audioconferenza Microsoft 365 o Office 365, Microsoft offre un ulteriore vantaggio gratuito relativo alla chiamata in uscita dalle riunioni organizzate da utenti a cui è assegnata una licenza di abbonamento Microsoft 365 o Office 365 audioconferenza fino a novembre 2019. Durante questo periodo gratuito, Microsoft consente agli organizzatori della riunione o ai partecipanti autorizzati, come definito nelle impostazioni dei criteri di riunione, di effettuare chiamate in uscita dall'interno della riunione a numeri di telefono non premium nei 44 paesi e aree geografiche dell'area [A.](audio-conferencing-zones.md) Questo vantaggio è applicabile alle licenze di abbonamento mensile per audioconferenze e non si estende alle licenze di audioconferenza a pagamento al minuto.

Inoltre, durante il periodo di chiamata in uscita gratuita è previsto un limite di 900 minuti:

Gli utenti con una posizione di utilizzo delle licenze (la località è il paese dell'utente definito nell'area delle licenze del interfaccia di amministrazione di Microsoft 365) _in_ qualsiasi _ paese possono effettuare chiamate in uscita da una conferenza in uno dei 44 paesi e aree geografiche dell'area [A.](audio-conferencing-zones.md) Ogni utente riceve 900 minuti per  utente al mese in uno dei paesi e aree geografiche dell'area [A,](audio-conferencing-zones.md)che sono in pool a livello di tenant. Ad esempio, un cliente ha acquistato 115 licenze di abbonamento per audioconferenza e ha 10 utenti negli Stati Uniti, 100 utenti nel Regno Unito e 5 utenti in India, tutti con licenze di abbonamento per audioconferenza assegnate agli utenti.

- Tutti i 115 utenti condividono un pool di (115 utenti X 900 min) = 103.500 minuti di chiamata in uscita per ogni mese di calendario, che può essere usato per effettuare chiamate in uscita verso uno dei paesi e delle aree geografiche [dell'area A.](audio-conferencing-zones.md)

- Tutte le chiamate che superano i 103.500 minuti al mese di calendario vengono fatturate al minuto usando i Crediti comunicazioni alle tariffe pubblicate per tale destinazione. Nota: il tenant deve configurare i Crediti comunicazioni e assegnare la licenza Crediti comunicazioni all'organizzatore della riunione.

- Tutte le chiamate in uscita verso destinazioni non presenti nell'elenco dei paesi e delle aree geografiche della zona [A](audio-conferencing-zones.md) vengono fatturate al minuto usando i Crediti comunicazioni alle tariffe pubblicate per tale destinazione (a condizione che il tenant abbia configurato crediti comunicazioni e assegnato la licenza Crediti comunicazioni all'organizzatore della riunione).

> [!NOTE]
> È possibile monitorare l'utilizzo rispetto al pool di minuti di chiamata in uscita nell'Skype for Business di amministrazione. Nell'Microsoft Teams & Skype di amministrazione passare a **Legacy Portal**  >  **Reports**  >  **PSTN Minute Pools**. Questo pool di minuti gratuito verrà etichettato nel report come "Chiamate in uscita verso paesi e aree geografiche della zona A".

Le notifiche tramite posta elettronica verranno inviate a tutti gli amministratori del tenant di un determinato cliente quando l'utilizzo del pool di minuti di chiamata in uscita del tenant ha raggiunto l'80% e il 100%.

Per le chiamate in uscita fatturate al minuto (chiamate che superano il pool di minuti di uscita del tenant o le chiamate verso destinazioni non presenti nell'elenco paesi e aree geografiche della zona [A),](audio-conferencing-zones.md) le chiamate e le relative tariffe sono basate principalmente sulla destinazione della chiamata e non sul paese o l'area geografica dell'organizzatore o del partecipante che avvia la chiamata in uscita. Ad esempio, una chiamata a un numero di telefono in Francia verrà fatturata con la stessa tariffa se viene avviata da un partecipante alla riunione negli Stati Uniti o da uno in Francia.

Per altre informazioni sui Crediti comunicazioni, vedere [Crediti comunicazioni](what-are-communications-credits.md).
     
## <a name="related-topics"></a>Argomenti correlati

- [Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Aree del paese e dell'area geografica per le audioconferenze](audio-conferencing-zones.md)
