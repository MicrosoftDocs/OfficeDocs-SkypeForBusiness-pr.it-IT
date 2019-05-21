---
title: Ulteriori informazioni su ID linea chiamante e nome del chiamante
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Informazioni sui motivi per cui è necessario aggiungere una persona autorizzata che può apportare modifiche all'account quando si usa la procedura guidata nuovo ordine di trasferimento dei numeri locali.
ms.openlocfilehash: e77176b978cb33df2bc4efebae11fb218c3932a5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293767"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Ulteriori informazioni su ID linea chiamante e nome del chiamante

Criteri ID chiamante, come si fa in genere, è costituito da due parti di informazioni identificabili che si trovano di fronte all'utente:
    - Numero di telefono (in genere denominato CLID o ID linea chiamante) 
    - Nome della festa chiamante (in genere indicato come CNAM) che può contenere fino a 15 caratteri di lunghezza. 

Quando viene effettuata una chiamata, il CLID (numero di telefono) viene indirizzato al vettore di destinazione (noto anche come elemento portante di terminazione). Le informazioni CNAM per la chiamata possono essere instradate o meno con la chiamata in quanto ciò dipende dal modo in cui il paese ha implementato CNAM (se non del tutto). L'affidabilità della consegna CNAM con la chiamata varia a seconda del paese e dei vettori che gestiscono la chiamata come intermediari e/o come gestore di terminazione. 

CLID & CNAM la trasmissione è la responsabilità del vettore di terminazione nella misura in cui il vettore di terminazione deve supportare le funzionalità di CLID & CNAM e consentire i record aggiornati per entrambi i valori. Microsoft fornisce in modo affidabile i valori di CLID in caso di chiamate di origine, ma tali valori potrebbero non essere mantenuti integri dopo il passaggio di un vettore intermedio o del vettore di terminazione. Purtroppo, se il valore di CLID viene modificato, omesso o troncato dall'intermediario o da un vettore di terminazione, Microsoft non ha alcun ricorso per correggere tali problemi nella rete telefonica pubblica.

Le incongruenze in CNAM possono essere causate da ritardi nei vettori intermedi o di terminazione che aggiornano le informazioni di CNAM nei database autorevoli, come nel caso degli Stati Uniti. In paesi in cui non esiste un database autorevole per CNAM, le singole procedure di trasporto possono anche causare problemi con le informazioni di CNAM che arrivano intatte con la chiamata. Microsoft attualmente non supporta l'origine di informazioni CNAM in paesi diversi dagli Stati Uniti. "

## <a name="related-topics"></a>Argomenti correlati


