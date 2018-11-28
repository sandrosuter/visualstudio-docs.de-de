---
title: Anonymisierung von Daten der Visual Studio-Abonnenten | Microsoft-Dokumentation
author: evanwindom
ms.author: lank
manager: lank
ms.date: 10/31/2018
ms.topic: conceptual
description: Erfahren Sie, wie Abonnentendaten anonymisiert werden, wenn der Zugriff auf Abonnements verloren gegangen ist.
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: 4570ff43f946c25c50d298e22de3b0c8a261f870
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51811250"
---
# <a name="anonymization-of-visual-studio-subscriber-information"></a>Anonymisierung von Informationen der Visual Studio-Abonnenten

Wenn ein Ereignis eintritt, durch das die Verwendung eines Abonnements durch einen Abonnenten blockiert wird, z.B. der Ablauf eines Abonnements oder die Löschung des Anmeldekontos eines Abonnenten, werden die persönlichen Informationen des Benutzers wie Name und Anmeldekonto so verschlüsselt, dass sie unbrauchbar werden.  Dies geschieht, um die persönlichen Informationen des Abonnenten zu schützen.

[!INCLUDE [GDPR-related guidance](includes/gdpr-intro-sentence.md)]

## <a name="when-does-anonymization-occur"></a>Wann kommt es zur Anonymisierung?

Ereignisse, die ein Abonnement für einen Abonnenten unbenutzbar machen, lösen eine Anonymisierung aus.  Wie schnell die Anonymisierung erfolgt, hängt von der Art des Abonnements und dem auslösenden Ereignis ab. Weitere Informationen finden Sie in der folgenden Tabelle.

| Abonnementtyp                                                                                                                       | Ereignis, das die Anonymisierung auslöst                                                                                                     | Wann es zur Anonymisierung kommt |
|-----------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|---------------------------|
| Visual Studio Dev Essentials                                                                                                            | Der Abonnent kündigt das Programm oder akzeptiert die Nutzungsbedingungen nicht                                    | 30 Tage               |
| Visual Studio-Abonnements, die über den Microsoft Store erworben wurden (Einzelhandel)                                                                      | Das Abonnement läuft ab oder wird nicht aktiviert                                                                   | 360 Tage                  |
| Visual Studio-Abonnements, die über Volumenlizenz, Visual Studio Marketplace (Cloud-Abonnements) oder Programme wie MPN erworben wurden | Das Abonnement läuft ab oder wird keinem Benutzer zugewiesen                                                          | 180 Tage                  |
| Alle Abonnements                                                                                                                       | Ein Azure Active Directory-Konto oder ein Microsoft-Konto (MSA), das für die Anmeldung beim Abonnement verwendet wird, wird geschlossen | Sofort               |
| Alle Abonnements                                                                                                                       | Ein Abonnent wird aus dem Mandanten entfernt, der mit dem Azure Active Directory-Konto verknüpft ist                                | Sofort               |

## <a name="faq"></a>FAQ

### <a name="q--does-the-anonymization-of-the-subscribers-personal-information-cause-them-to-lose-access-to-the-subscription"></a>F: Führt die Anonymisierung der persönlichen Informationen des Abonnenten dazu, dass er den Zugriff auf das Abonnement verliert?
A: Nein.  Die Anonymisierung ist eine Reaktion auf ein Ereignis, durch das der Zugriff auf das Abonnement verloren geht, aber nicht die Ursache für den Verlust des Zugriffs.

### <a name="q--im-an-administrator-for-my-organizations-subscriptions--if-one-of-my-subscribers-information-is-anonymized-can-that-subscription-be-reassigned-to-another-user"></a>F: Ich bin ein Administrator für die Abonnements meiner Organisation.  Wenn die Informationen eines meiner Abonnenten anonymisiert werden, kann dieses Abonnement dann einem anderen Benutzer zugewiesen werden?
A: Ja, solange das Abonnement nicht abgelaufen ist, kann es einem anderen Abonnenten zugewiesen werden.

## <a name="next-steps"></a>Nächste Schritte

Informationen zum Verhindern der Anonymisierung durch Verbinden von MSA- und AAD-Identitäten erhalten Sie unter [Hinzufügen von Azure Active Directory B2B-Zusammenarbeitsbenutzern über das Azure-Portal](/azure/active-directory/b2b/add-users-administrator).