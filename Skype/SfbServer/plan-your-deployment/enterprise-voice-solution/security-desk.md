---
title: Includere lo sportello di sicurezza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Pianificare come includere il desk di sicurezza dell'organizzazione in una distribuzione di E9-1-1, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 7be3533879f36c897d148194345e1496945359b6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187562"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a>Includere lo sportello di sicurezza in Skype for Business Server
 
Pianificare come includere il desk di sicurezza dell'organizzazione in una distribuzione di E9-1-1, in Skype for Business Server VoIP aziendale.
  
La società può richiedere che il servizio di sicurezza venga coinvolto in una chiamata di emergenza. Per decidere come integrare il servizio di sicurezza nella distribuzione di E9-1-1, è necessario rispondere alle domande seguenti.
  
**Si vuole che il desk di sicurezza venga avvisato quando è presente una chiamata di emergenza?**
  
È possibile configurare i criteri di posizione in modo che Skype for Business Server invii avvisi di messaggistica istantanea agli indirizzi SIP di Skype for business di uno o più addetti alla sicurezza. Questi avvisi contengono il nome, il numero e la posizione della persona che effettua la chiamata di emergenza e facilitano il personale di sicurezza nell'assistenza per la situazione di emergenza.
    
**Si vuole eseguire una conferenza sul banco di sicurezza in ogni chiamata di emergenza?**
  
Se supportato dal provider del servizio servizi di emergenza, è possibile configurare i criteri di posizione per includere un numero di callback con ogni chiamata di emergenza. Questo numero viene quindi usato dal provider per organizzare il personale di sicurezza dell'organizzazione in chiamate di emergenza. Questa conferenza può essere configurata nel criterio della posizione in modo unidirezionale (solo in ascolto) o bidirezionale (bidirezionali).
    
> [!NOTE]
> Se lo si desidera, è possibile configurare personale di emergenza diverso per ogni criterio di posizione. In questo modo, puoi personalizzare la risposta per diverse aree all'interno della tua azienda oppure creare comportamenti diversi per le chiamate di emergenza che hanno origine dall'interno invece che all'esterno della rete. È possibile usare i gruppi di distribuzione per specificare il personale che si vuole inviare. 
  

