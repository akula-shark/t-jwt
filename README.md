# Is this library safe for production?
Not yet. This will be updated when it eventually is tested and verified by a third-party.

# What is a JWT?

JWT stands for JSON Web Token, which is a compact and secure way to transmit data between parties in a JSON format. JWTs are used for authentication and authorization purposes and consist of three parts: a header, a payload, and a signature. The header contains information about the algorithm used to sign the token, the payload contains the user's data or claims, and the signature is used to verify the token's authenticity. JWTs are commonly used in web applications, APIs, and mobile applications.

A JWT Looks roughly like:
xxxxx.yyyyy.zzzzz

# Getting started

```dart
import 'package:t_jwt/t_jwt.dart';

void main() {
  var jwt = JWT();

  var header = {
    'alg': 'HS256',
    'typ': 'JWT'
  };

  var payload = {
    'name': 'Topography Digital',
    'username': 'topography.digital',
  };

  DateTime expiresAt = DateTime.now().add(Duration(days: 1));

  String signed = jwt.sign(header, payload, expiresAt);

  bool isVerified = jwt.verify(signed);

  print(signed);
  print(isVerified);
}
```
