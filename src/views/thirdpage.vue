
<script setup lang="ts">
import { reactive,ref } from 'vue';
import router from '@/router';
// @ts-ignore

import { useInputStore } from "../stores/inputstore";
const inputStore = useInputStore();

const next = () => {
    console.log(all);

    if (all.address && all.home_phone && all.housing_status &&
        all.father_phone && all.mother_phone && all.phone &&
        all.emergency_phone && all.children_before && all.family_members
        && all.study_room && all.live_with && all.housing_situation &&
        all.student_supervisor && all.email && all.height && all.weight) {
        if (all.student_supervisor === 'sayer') {
            if (!(all.supervisor_birth_day && all.supervisor_birth_month
                && all.supervisor_birth_year&&all.supervisor_name&&all.supervisor_id&&all.supervisor_national_code
                && all.supervisor_insurance_code &&all.supervisor_occupation&&all.supervisor_work_address
                &&all.supervisor_work_phone)) {
                alert('اطلاعات درست نیست!');

                return;
            }
        }

        inputStore.setInputValue("address", all.address);
        inputStore.setInputValue("home_phone", all.home_phone);
        inputStore.setInputValue("housing_status", all.housing_status);
        inputStore.setInputValue("father_phone", all.father_phone);
        inputStore.setInputValue("mother_phone", all.mother_phone);
        inputStore.setInputValue("phone", all.phone);
        inputStore.setInputValue("emergency_phone", all.emergency_phone);
        inputStore.setInputValue("children_before", all.children_before);
        inputStore.setInputValue("family_members", all.family_members);
        inputStore.setInputValue("study_room", all.study_room);
        inputStore.setInputValue("live_with", all.live_with);
        inputStore.setInputValue("housing_situation", all.housing_situation);
        inputStore.setInputValue("student_supervisor", all.student_supervisor);
        inputStore.setInputValue("supervisor_birth_day", all.supervisor_birth_day);
        inputStore.setInputValue("supervisor_birth_month", all.supervisor_birth_month);
        inputStore.setInputValue("supervisor_birth_year", all.supervisor_birth_year);
        inputStore.setInputValue("supervisor_name", all.supervisor_name);
        inputStore.setInputValue("supervisor_national_code", all.supervisor_national_code);
        inputStore.setInputValue("supervisor_id", all.supervisor_id);
        inputStore.setInputValue("supervisor_occupation", all.supervisor_occupation);
        inputStore.setInputValue("supervisor_work_address",all.supervisor_work_address)
        inputStore.setInputValue("supervisor_insurance_code",all.supervisor_insurance_code)
        inputStore.setInputValue("supervisor_work_phone",all.supervisor_work_phone)
        inputStore.setInputValue("supervisor_issue_place",all.supervisor_issue_place)

        
        inputStore.setInputValue("email", all.email);
        inputStore.setInputValue("height", all.height);
        inputStore.setInputValue("weight", all.weight);
        inputStore.setInputValue("ability", all.ability);

        router.push('/fourthpage')

    }
    else {
        alert('اطلاعات درست نیست!');
    }




}
const back =()=>{
    router.push('/secondpage')
}
const all = reactive({
    address: inputStore.address,
    home_phone: inputStore.home_phone,
    housing_status: inputStore.housing_status,
    father_phone: inputStore.father_phone,
    mother_phone: inputStore.mother_phone,
    phone: inputStore.phone,
    emergency_phone: inputStore.emergency_phone,
    children_before: inputStore.children_before,
    family_members: inputStore.family_members,
    study_room: inputStore.study_room,
    live_with: inputStore.live_with,
    housing_situation: inputStore.housing_situation,
    student_supervisor: inputStore.student_supervisor,
    supervisor_birth_day: inputStore.supervisor_birth_day,
    supervisor_birth_month: inputStore.supervisor_birth_month,
    supervisor_birth_year: inputStore.supervisor_birth_year,
    supervisor_name:inputStore.supervisor_name,
    supervisor_national_code:inputStore.supervisor_national_code,
    supervisor_id:inputStore.supervisor_id,
    supervisor_education:inputStore.supervisor_education,
    supervisor_occupation:inputStore.supervisor_occupation,
    supervisor_work_address:inputStore.supervisor_work_address,
    supervisor_insurance_code:inputStore.supervisor_insurance_code,
    supervisor_work_phone:inputStore.supervisor_work_phone,
    supervisor_issue_place:inputStore.supervisor_issue_place,
    email: inputStore.email,
    height: inputStore.heught,
    weight: inputStore.weight,
    ability: inputStore.ability,
    










})
//1
const error_1 = ref()
function onInput_1(e:any) {
  const value = e.target.value

  if (isNaN(value)) {
    error_1.value = true
  } else {
    error_1.value = false

  }
}
//2
const error_2 = ref()
function onInput_2(e:any) {
  const value = e.target.value

  if (isNaN(value)|| !all.father_phone.startsWith('09')|| all.father_phone.length > 11|| all.father_phone.length < 11) {
    error_2.value = true
  } else {
    error_2.value = false

  }
}
//3
const error_3 = ref()
function onInput_3(e:any) {
  const value = e.target.value

  if (isNaN(value)|| !all.mother_phone.startsWith('09')|| all.mother_phone.length > 11|| all.mother_phone.length < 11) {
    error_3.value = true
  } else {
    error_3.value = false

  }
}
//4
const error_4 = ref()
function onInput_4(e:any) {
  const value = e.target.value

  if (isNaN(value)|| !all.phone.startsWith('09')|| all.phone.length > 11|| all.phone.length < 11) {
    error_4.value = true
  } else {
    error_4.value = false

  }
}
//5
const error_5 = ref()
function onInput_5(e:any) {
  const value = e.target.value

  if (isNaN(value)) {
    error_5.value = true
  } else {
    error_5.value = false
  }
}
//6
const error_6= ref()
const error_lenght_1 = ref ()
function onInput_6 (e:any){
    const value = e.target.value

if (isNaN(value) ) {
  error_6.value = true
} 
else if(all.supervisor_birth_day.length > 2){
error_lenght_1.value = true
}
else if (all.supervisor_birth_day.length>0){
    error_6.value = false
    error_lenght_1.value = false

}

else if (all.supervisor_birth_day.length < 3){
    error_lenght_1.value = false

}
else {
  error_6.value = false
}
}
const error_7= ref()
const error_lenght_2 = ref ()
function onInput_7 (e:any){
    const value = e.target.value

if (isNaN(value) ) {
  error_7.value = true
} 
else if(all.supervisor_birth_month.length > 2){
error_lenght_2.value = true
}
else if (all.supervisor_birth_month.length>0){
    error_7.value = false
    error_lenght_2.value = false

}

else if (all.supervisor_birth_month.length < 3){
    error_lenght_2.value = false

}
else {
  error_7.value = false
}
}
const error_8= ref()
const error_lenght_3 = ref ()
function onInput_8 (e:any){
    const value = e.target.value

if (isNaN(value) ) {
  error_8.value = true
} 
else if(all.supervisor_birth_year.length > 2){
error_lenght_3.value = true
}
else if (all.supervisor_birth_year.length>0){
    error_8.value = false
    error_lenght_3.value = false

}

else if (all.supervisor_birth_year.length < 3){
    error_lenght_3.value = false

}
else {
  error_8.value = false
}
}
//9
const error_9 = ref(false) 

function onInput_9() {
    var xv = all.supervisor_national_code ;
    if (isNaN(xv)) {
        error_9.value = true
    } else if (xv == "") {
        error_9.value = true
    } else if (xv.length < 10) {
        error_9.value = true
    } else {
        var yy = 0;
        var yv = parseInt(xv);
        for (let i = 0; i < xv.length; i++) {
            yv = xv[i] * (xv.length - i);
            yy += yv;
        }
        var x = yy % 11;
        if (x === 0) {
            error_9.value = false
        } else {
            error_9.value = false
        }
        yy = 0;
    }
}
//10
const error_10 = ref()
function onInput_10(e:any) {
  const value = e.target.value

  if (isNaN(value)) {
    error_10.value = true
  } else {
    error_10.value = false
  }
}
//11
const error_11 = ref(false)
function onInput_11(e:any){
  const value = e.target.value
  if (isNaN(value)|| all.supervisor_insurance_code.length > 8|| all.supervisor_insurance_code.length < 8){
    error_11.value = true
  }
   else {
    error_11.value = false
  }
}
//12
const error_12 = ref(false)
function onInput_12(e:any) {
  const value = e.target.value
  if (isNaN(value)) {
    error_12.value = true
  } else {
    error_12.value = false

  }
}

// const error_9 = ref()
// function onInput_9(e:any) {
//   const value = e.target.value

//   if (isNaN(value)||all.email.endsWith("@gmail.com")) {
//     error_9.value = true
//   } else {
//     error_9.value = false
//   }
// }
</script>
<template>
    <main style="padding-bottom:;">
        <br>
        <br>
        <br>
        <br>
        <br>
    <div class="container"
        style="font-family: B Homa; text-align: right; background-color: rgba(255, 255, 255, 0.76); padding: 30px; border-radius: 20px; backdrop-filter: blur(10px);"
        dir="rtl">

        <div class="row">


            <div class="col-md-4">
                <div class="form-group">
                    <label>آدرس منزل</label>
                    <input type="text" class="form-control" name="address" v-model="all.address">
                </div>
            </div>
            <div class="col-md-4">
                <div class="form-group">
                    <label>تلفن منزل</label>
                    <input @input="onInput_1" title="فقط عدد وارد کنید!" type="text" class="form-control" name="home_phone"
                        v-model="all.home_phone">
                        <p v-if="error_1" style="color: red;">شماره تلفن اشتباه است!</p>


                </div>
            </div>
            <div class="col-md-4">
                <div class="form-group">
                    <label>وضعیت مسکن</label>
                    <select required class="form-control" name="housing_status" v-model="all.housing_status">
                        <option disabled selected>وضعیت مسکن</option>
                        <option>اجارهای</option>
                        <option>ملک شخصی</option>
                        <option>خانه سازمانی</option>
                        <option>سایر</option>

                    </select>
                </div>
            </div>
        </div>


        <div class="row">

            <div class="col-md-4">
                <div class="form-group">
                    <label>تلفن همراه پدر</label>
                    <input @input="onInput_2" title="فقط عدد وارد کنید!" type="text" class="form-control" name="father_phone"
                        v-model="all.father_phone">
                        <p v-if="error_2" style="color: red;">شماره تلفن اشتباه است!</p>

                </div>
            </div>

            <div class="col-md-4">
                <div class="form-group">
                    <label>تلفن همراه مادر</label>
                    <input @input="onInput_3" title="فقط عدد وارد کنید!" type="text" class="form-control" name="mother_phone"
                        v-model="all.mother_phone">
                        <p v-if="error_3" style="color: red;">شماره تلفن اشتباه است!</p>

                </div>
            </div>
            <div class="col-md-4">
                <div class="form-group">
                    <label>تلفن همراه دانش آموز</label>
                    <input @input="onInput_4" title="فقط عدد وارد کنید!" type="text" class="form-control" name="phone" v-model="all.phone">
                    <p v-if="error_4" style="color: red;">شماره تلفن اشتباه است!</p>

                </div>
            </div>
        </div>

        <div class="row">



            <div class="col-md-4">
                <div class="form-group">
                    <label>تلفن اضطراری</label>
                    <input @input="onInput_5" title="فقط عدد وارد کنید!" type="text" class="form-control" name="emergency_phone"
                        v-model="all.emergency_phone">
                        <p v-if="error_5" style="color: red;">شماره تلفن اشتباه است!</p>


                </div>
            </div>

            <div class="col-md-4">
                <div class="form-group">
                    <label>چندمین فرزند است؟</label>
                    <select required class="form-control" name="children_before" v-model="all.children_before">
                        <option disabled selected></option>
                        <option>اولین(بزرگ ترین)</option>
                        <option>آخرین (کوچک ترین)</option>
                        <option>دومین</option>
                        <option>سومین</option>
                        <option>چهارمین</option>
                        <option>پنجمین</option>
                        <option>ششمین</option>
                        <option>هفتمین</option>
                        <option>هشتمین</option>
                        <option>نهمین</option>
                        <option>دهمین</option>
                    </select>
                </div>
            </div>

            <div class="col-md-4">
                <div class="form-group">
                    <label>تعداد افراد خانواده</label>
                    <select required class="form-control" name="family_members" v-model="all.family_members">
                        <option disabled selected></option>
                        <option>1</option>
                        <option>2</option>
                        <option>3</option>
                        <option>4</option>
                        <option>5</option>
                        <option>6</option>
                        <option>7</option>
                        <option>8</option>
                        <option>9</option>
                        <option>10</option>
                        <option>11</option>
                        <option>12</option>



                    </select>
                </div>
            </div>

        </div>

        <div class="row">
            <div class="col-md-6">
                <div class="form-group">
                    <label>آیا هنرجو اتاق مستقل مطالعه دارد؟</label>
                    <select required class="form-control" name="study_room" v-model="all.study_room">
                        <option disabled selected></option>
                        <option>بله</option>
                        <option>خیر</option>
                    </select>
                </div>
            </div>
            <div class="col-md-6">
                <div class="form-group">
                    <label>هنرجو در خانواده با چه کسانی زندگی میکند</label>
                    <select required class="form-control" name="live_with" v-model="all.live_with">
                        <option disabled selected></option>
                        <option>پدر و مادر</option>
                        <option>پدر</option>
                        <option>مادر</option>
                        <option>پدر و مادر خوانده</option>
                        <option>مادر بزگ یا پدر بزرگ</option>
                        <option>سایر بستگان</option>
                        <option>پرورشگاه</option>
                        <option>مستقل</option>

                    </select>
                </div>

            </div>
        </div>



        <div class="row">
            <div class="col-md-8">
                <div class="form-group">
                    <label>وضعیت مسکن هنرجو در صورتی که برای تحصیل دور از خانواده زندگی می گند</label>
                    <select required class="form-control" name="housing_situation" v-model="all.housing_situation">
                        <option disabled selected></option>
                        <option>ملک شخصی</option>
                        <option>خوابگاه دانش آموزی</option>
                        <option>مسکن اجاره ای</option>
                        <option>منزل بستگان</option>
                        <option>سایر</option>


                    </select>
                </div>



            </div>

            <div class="col-md-4">
                <div class="form-group">
                    <label>ولی / سرپرست هنرجو کیست؟</label>
                    <select id="sarparast" required class="form-control" name="student_supervisor"
                        v-model="all.student_supervisor">
                        <option disabled selected></option>
                        <option value="پدر">پدر</option>
                        <option value="مادر">مادر</option>
                        <option value="سایر">سایر</option>

                    </select>
                </div>
            </div>
        </div>
        <div class="row" v-if="all.student_supervisor === 'سایر'">
            <div class="col-md-2">
                <div class="form-group">
                    <label>روز تولد سرپرست</label>
                    <input @input="onInput_6" title="فقط عدد وارد کنید!" type="text" class="form-control" name="supervisor_birth_day"
                        v-model="all.supervisor_birth_day">
                        <p v-if="error_6" style="color: red;">لطفا فقط عدد وارد کنید!</p>
                        <p v-if="error_lenght_1" style="color: red;">اعداد بیش از حد است!</p>
                </div>
            </div>
            <div class="col-md-2">
                <div class="form-group">
                    <label>ماه تولد سرپرست</label>
                    <input @input="onInput_7" title="فقط عدد وارد کنید!" type="text" class="form-control" name="supervisor_birth_month"
                        v-model="all.supervisor_birth_month">
                        <p v-if="error_7" style="color: red;">لطفا فقط عدد وارد کنید!</p>
                        <p v-if="error_lenght_2" style="color: red;">اعداد بیش از حد است!</p>
                </div>
            </div>
            <div class="col-md-2">
                <div class="form-group">
                    <label>سال تولد سرپرست</label>
                    <input @input="onInput_8" title="فقط عدد وارد کنید!" type="text" class="form-control" name="supervisor_birth_year"
                        v-model="all.supervisor_birth_year">
                        <p v-if="error_8" style="color: red;">لطفا فقط عدد وارد کنید!</p>
                        <p v-if="error_lenght_3" style="color: red;">اعداد بیش از حد است!</p>
                </div>
            </div>
            <div class="col-md-6">
                <div class="form-group">
                    <label>نام و نام خانوادگی سرپرست</label>
                    <input  type="text" class="form-control" name="supervisor_birth_year"
                        v-model="all.supervisor_name">
                </div>
            </div>
            <div class="col-md-4">
                <div class="form-group">
                    <label>کد ملی سرپرست</label>
                    <input @input="onInput_9" type="text" class="form-control" name="supervisor_birth_year"
                        v-model="all.supervisor_national_code">
                        <p v-if="error_9" style="color: red;">کد ملی اشتباه است!</p>

                </div>

            </div>
            <div class="col-md-4">
                <div class="form-group">
                    <label>شماره شناسنامه سرپرست</label>
                    <input @input="onInput_10" type="text" class="form-control" name="supervisor_birth_year"
                        v-model="all.supervisor_id">
                        <p v-if="error_10" style="color: red;">لطفا فقط عدد وارد کنید!</p>

                </div>
                
            </div>
            <div class="col-md-4">
                <div class="form-group">
                    <label>تحصیلات سرپرست</label>
                    <select required class="form-control" name="father_education" v-model="all.supervisor_education">
                        <option disabled selected>تحصیلات سرپرست</option>
                        <option>بی سواد</option>
                        <option>ابتدایی</option>
                        <option>سیکل</option>
                        <option>دیپلم</option>
                        <option>فوق دیپلم</option>
                        <option>لیسانس</option>
                        <option>فوق لیسانس</option>
                        <option>دکتری</option>
                        <option>حوزه علمیه</option>
                        <option>سایر</option>
                    </select>
                </div>
            </div>
            <div class="col-md-4">
                <div class="form-group">
                    <label>شغل سرپرست</label>
                    <select required class="form-control" name="father_occupation" v-model="all.supervisor_occupation">
                        <option disabled selected>شغل سرپرست</option>
                        <option>فوت شده</option>
                        <option>فرهنگی</option>
                        <option>کارمند</option>
                        <option>بازنشسته</option>
                        <option>کارگر</option>
                        <option>کشاورز</option>
                        <option>دامدار</option>
                        <option>از کار افتاده</option>
                        <option>بیکار</option>
                        <option>راننده</option>
                        <option>آزاد</option>
                        <option>سایر</option>
                    </select>
                </div>
            </div>
            <div class="col-md-4">
                <div class="form-group">
                    <label>آدرس محل کار سرپرست</label>
                    <input type="text" class="form-control" name="father_work_address" v-model="all.supervisor_work_address">
                </div>
            </div>
            <div class="col-md-4">
                <div class="form-group">
                    <label>محل صدور شناسنامه سرپرست</label>
                    <input type="text" class="form-control" name="father_work_address" v-model="all.supervisor_issue_place">
                </div>
            </div>
                 <div class="col-md-3">
                <div class="form-group">
                    <label>کد بیمه سرپرست</label>
                    <input @input="onInput_11" type="text" title="فقط عدد وارد کنید!" class="form-control" name="father_insurance_code"
                        v-model="all.supervisor_insurance_code">
                        <p v-if="error_11" style="color: red;">کد بیمه اشتباه است!</p>
                </div>
            </div>
            <div class="col-md-4">
                <div class="form-group">
                    <label>تلفن محل کار سرپرست</label>
                    <input @input="onInput_12" type="text" title="فقط عدد وارد کنید!" class="form-control" name="father_work_phone"
                        v-model="all.supervisor_work_phone">
                        <p v-if="error_12" style="color: red;">شماره تلفن اشتباه است!</p>

                </div>

            </div>

        </div>



        <div class="row">

            <div class="col-md-4">
                <div class="form-group">
                    <label>ایمیل</label>
                    <input  type="email" class="form-control" name="email" v-model="all.email">


                </div>
            </div>

            <div class="col-md-4">
                <div class="form-group">
                    <label>قد (سانتی متر)</label>
                    <input title="فقط عدد وارد کنید!" type="text" class="form-control" name="height" v-model="all.height">
                </div>
            </div>

            <div class="col-md-4">
                <div class="form-group">
                    <label>وزن (کیلو گرم)</label>
                    <input title="فقط عدد وارد کنید!" type="text" class="form-control" name="weight" v-model="all.weight">
                </div>
            </div>
        </div>

        <div class="row">


            <div class="col-md-12">
                <div class="form-group">
                    <label>توانایی (کسب مقام و رتبه) </label>
                    <input type="text" class="form-control" name="ability" v-model="all.ability">
                </div>
            </div>

        </div>
        <button type="submit" class="btn btn-primary" @click="next()">بعدی</button>
        <button style="float: left;" type="submit" class="btn btn-primary" @click="back()">بازگشت</button>


    </div>
</main>
</template>