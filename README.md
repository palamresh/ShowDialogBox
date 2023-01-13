# ShowDialogBox

import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(home: MyHomePage()));
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key});

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
        appBar: AppBar(
          title: const Text('FormField Example'),
        ),
        body: Center(
          child: ElevatedButton(
            onPressed: () {
              showDialog(
                  context: context,
                  builder: (context) {
                    return Container(
                        child: AlertDialog(
                      content: TextField(
                        onChanged: (value) {
                          print("some of two number");
                        },
                        decoration:
                            InputDecoration(label: Text('Enter your name')),
                      ),
                      title: const Text('Email send'),
                      actions: [
                        TextButton(
                            onPressed: () {
                              Navigator.pop(context);
                            },
                            child: Text('Yes')),
                        TextButton(
                            onPressed: () {
                              Navigator.pop(context);
                            },
                            child: Text('NO'))
                      ],
                    ));
                  });
            },
            child: const Text('Show DialogBox'),
          ),
        ));
  }
}
