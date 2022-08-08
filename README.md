# Easy SharedPreference Kotlin Android

package com.example.easysharedpreference

import android.content.Context
import android.content.SharedPreferences
import com.example.easysharedpreference.Constants.PREF_FILE

object PrefUtil {
    private var sharedPreferences: SharedPreferences? = null

    fun initPrefUtil(context: Context) {
        sharedPreferences =
            context.getSharedPreferences(PREF_FILE, 0)
    }

    fun saveData(key: String, value: String) {
        val prefsEditor = sharedPreferences?.edit()
        prefsEditor?.putString(key, value)?.apply()
    }

    fun getData(key: String): String {
        return sharedPreferences?.getString(key, "").toString()
    }
}
