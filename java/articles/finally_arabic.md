<!--
Meta Description: # استخدام الكلمة المحجوزة "finally" في جافا: الدليل الشامل ## الملخص تُستخدم الكلمة المحجوزة "finally" في جافا لضمان تنفيذ الكود بغض النظر عن كيفية إن...
Meta Keywords: finally, catch, try, كتلة, استخدام
-->

# استخدام الكلمة المحجوزة "finally" في جافا: الدليل الشامل

## الملخص
تُستخدم الكلمة المحجوزة "finally" في جافا لضمان تنفيذ الكود بغض النظر عن كيفية إنهاء البلوك الرئيسي، سواءً كان ذلك عن طريق استثناء أو انتهاء عادي. 

## الوثائق
تعتبر "finally" جزءًا من معالجة الاستثناءات في جافا. يُستخدم هذا الكود بعد كتلة try و catch. الهدف من "finally" هو تنفيذ كود معين بعد انتهاء كتلة try أو catch، مما يضمن تنظيف الموارد أو تنفيذ التعليمات الضرورية.

### الغرض
تساعد "finally" في ضمان تنفيذ التعليمات البرمجية التي تحتاج إلى التنفيذ دائمًا، مثل إغلاق الملفات أو تحرير الموارد.

### الاستخدام
عند استخدام "finally"، يتم وضعه بعد كتلة try و catch. يمكن أن تحتوي الكتلة "finally" على أي نوع من التعليمات البرمجية، وسيتم تنفيذها في جميع الحالات.

### التفاصيل
- يمكن أن تحتوي على كود إغلاق الملفات أو التحميلات أو أي موارد تحتاج إلى تحرير.
- تعمل "finally" حتى في حالة وجود استثناء غير معالج.
- يمكن أن تحتوي الكتلة "finally" على تعابير أو تعليمات برمجية أخرى.

## الأمثلة
### مثال 1: استخدام "finally" مع try و catch
```java
public class FinallyExample {
    public static void main(String[] args) {
        try {
            int data = 25 / 0; // سيؤدي إلى استثناء
        } catch (ArithmeticException e) {
            System.out.println("استثناء: " + e.getMessage());
        } finally {
            System.out.println("كتلة finally تم التنفيذ");
        }
    }
}
```

### مثال 2: استخدام "finally" مع موارد
```java
import java.io.FileReader;
import java.io.BufferedReader;
import java.io.IOException;

public class FinallyResourceExample {
    public static void main(String[] args) {
        BufferedReader reader = null;
        try {
            reader = new BufferedReader(new FileReader("testfile.txt"));
            System.out.println(reader.readLine());
        } catch (IOException e) {
            System.out.println("استثناء: " + e.getMessage());
        } finally {
            try {
                if (reader != null) {
                    reader.close(); // تأكد من إغلاق الملف
                }
            } catch (IOException e) {
                System.out.println("استثناء أثناء إغلاق الملف: " + e.getMessage());
            }
            System.out.println("كتلة finally تم التنفيذ");
        }
    }
}
```

## الشرح
- **الأخطاء الشائعة**: قد يعتقد البعض أن "finally" ليست ضرورية إذا كان هناك كتلة catch. ولكن في بعض الحالات، مثل فتح اتصالات الشبكة أو الملفات، فإن استخدام "finally" يكون أمرًا ضروريًا لضمان عدم ترك الموارد مفتوحة.
- **ملاحظة إضافية**: إذا تم استخدام "return" داخل كتلة try أو catch، فإن "finally" ستظل تعمل، مما قد يؤدي إلى نتائج غير متوقعة إذا لم يتم الانتباه.

## ملخص من جملة واحدة
تضمن الكلمة المحجوزة "finally" في جافا تنفيذ التعليمات البرمجية المهمة دائمًا، بغض النظر عن كيفية إنهاء الكود في كتلة try أو catch.