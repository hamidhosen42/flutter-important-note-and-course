# flutter-important-note

### Animated Builder

```
// ignore_for_file: library_private_types_in_public_api, prefer_const_literals_to_create_immutables, unused_field, prefer_const_constructors, sized_box_for_whitespace

import 'package:flutter/material.dart';
import 'dart:math' as math;

import 'package:flutter_screenutil/flutter_screenutil.dart';

class SplashScreen extends StatefulWidget {
  const SplashScreen({Key? key}) : super(key: key);

  @override
  _SplashScreenState createState() => _SplashScreenState();
}

class _SplashScreenState extends State<SplashScreen>
    with TickerProviderStateMixin {
  late final AnimationController _controller =
      AnimationController(duration: Duration(seconds: 3), vsync: this)
        ..repeat();

  @override
  void initState() {
    // ignore: todo
    // TODO: implement initState
    super.initState();
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: SafeArea(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          crossAxisAlignment: CrossAxisAlignment.center,
          children: [
            Center(
              child: AnimatedBuilder(
                  animation: _controller,
                  child: Container(
                    width: 200.w,
                    height: 200.h,
                    child: Center(child: Image.asset("image/virus.png")),
                  ),
                  builder: (BuildContext context, child) {
                    return Transform.rotate(
                      angle: _controller.value * 2.0 * math.pi,
                      child: child,
                    );
                  }),
            )
          ],
        ),
      ),
    );
  }
}
```
