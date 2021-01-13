---
title: Includere il desk di sicurezza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Pianificazione del modo in cui includere il desk di sicurezza dell'organizzazione in una distribuzione di E9-1-1, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 756af940eb327bc4744454e9ed9ef7a7fbfd517d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813406"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a>Includere il desk di sicurezza in Skype for Business Server
 
Pianificazione del modo in cui includere il desk di sicurezza dell'organizzazione in una distribuzione di E9-1-1, in Skype for Business Server VoIP aziendale.
  
Nella propria azienda potrebbe essere necessario coinvolgere il desk di sicurezza in una chiamata di emergenza. Per decidere come integrare il desk di sicurezza nella distribuzione del servizio per chiamate di emergenza E9-1-1, è consigliabile rispondere alle domande riportate di seguito.
  
**Si desidera che il desk di sicurezza riceva notifica in caso di una chiamata di emergenza?**
  
È possibile configurare il criterio percorso in modo che Skype for Business Server invii avvisi di messaggistica istantanea agli indirizzi SIP di Skype for business di uno o più addetti alla sicurezza. Questi avvisi contengono il nome, il numero e la posizione della persona che effettua la chiamata di emergenza e consentono al personale della sicurezza di fornire più facilmente assistenza per la situazione di emergenza.
    
**Si desidera invitare il desk di sicurezza in conferenza per ogni chiamata di emergenza?**
  
Se supportato dal provider dei servizi di emergenza, è possibile configurare i criteri di percorso in modo da includere un numero di richiamata per ogni chiamata di emergenza. Questo numero viene quindi utilizzato dal provider per invitare il personale della sicurezza dell'organizzazione a partecipare in conferenza alle chiamate di emergenza. Nei criteri di percorso, questa funzionalità di conferenza può essere configurata come unidirezionale (solo ascolto) o bidirezionale.
    
> [!NOTE]
> Se lo si desidera, è possibile configurare personale di emergenza diverso per i singoli criteri di percorso. In questo modo è possibile personalizzare la risposta per aree diverse nella società o creare comportamenti diversi per le chiamate di emergenza che hanno origine dall'interno anziché dall'esterno della rete. Per specificare il personale a cui inviare la notifica, è possibile usare gruppi di distribuzione. 
  

