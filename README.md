// انسخ هذا الكود في Dcoder
// هذا نموذج عملي سيبيع

import 'package:flutter/material.dart';

void main() => runApp(TeacherApp());

class TeacherApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'المعلم الذكي - النسخة التجارية',
      theme: ThemeData(
        primarySwatch: Colors.green,
        fontFamily: 'Tajawal',
      ),
      home: SalesPage(), // صفحة البيع
    );
  }
}

class SalesPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('المعلم الذكي - الإصدار التجاري'),
        backgroundColor: Colors.green,
      ),
      body: Padding(
        padding: EdgeInsets.all(20),
        child: Column(
          children: [
            // شعار التطبيق
            Icon(Icons.school, size: 100, color: Colors.green),
            SizedBox(height: 20),
            
            // عنوان جذاب
            Text(
              'حول هاتفك إلى منصة تعليمية تدر عليك دخلاً!',
              style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
              textAlign: TextAlign.center,
            ),
            
            SizedBox(height: 20),
            
            // ميزات
            FeatureItem('إدارة الفصول والطلاب'),
            FeatureItem('نظام المكافآت التحفيزي'),
            FeatureItem('تقارير أداء مفصلة'),
            FeatureItem('تحقيق دسل من العمولات'),
            
            SizedBox(height: 30),
            
            // أسعار
            PriceCard('نسخة أساسية', '50 ر.س/شهر'),
            PriceCard('نسخة محترفة', '100 ر.س/شهر'),
            PriceCard('باقة مدرسة', '500 ر.س/شهر'),
            
            SizedBox(height: 20),
            
            // زر الاتصال
            ElevatedButton(
              onPressed: () {
                // سيأخذ العميل لرقم واتساب
              },
              child: Text('🚀 اطلب نسختك الآن'),
              style: ElevatedButton.styleFrom(
                backgroundColor: Colors.green,
                padding: EdgeInsets.symmetric(horizontal: 40, vertical: 15),
              ),
            ),
          ],
        ),
      ),
    );
  }
}

class FeatureItem extends StatelessWidget {
  final String text;
  FeatureItem(this.text);
  
  @override
  Widget build(BuildContext context) {
    return ListTile(
      leading: Icon(Icons.check_circle, color: Colors.green),
      title: Text(text),
    );
  }
}

class PriceCard extends StatelessWidget {
  final String title;
  final String price;
  PriceCard(this.title, this.price);
  
  @override
  Widget build(BuildContext context) {
    return Card(
      child: ListTile(
        title: Text(title, style: TextStyle(fontWeight: FontWeight.bold)),
        trailing: Text(price, style: TextStyle(color: Colors.green, fontWeight: FontWeight.bold)),
      ),
    );
  }
}
