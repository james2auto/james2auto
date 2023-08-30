<?php

namespace App\Http\Controllers;

use Illuminate\Http\Request;

class QuoteController extends Controller
{
    public function index()
    {
        return view('quote.index');
    }

    public function store(Request $request)
    {
        $request->validate([
            'name' => 'required',
            'phone_number' => 'required',
            'email' => 'required|email',
        ]);

        $quote = new Quote();
        $quote->name = $request->name;
        $quote->phone_number = $request->phone_number;
        $quote->email = $request->email;
        $quote->save();

        return redirect()->route('quote.index')->with('success', 'Quote created successfully!');
    }
}

<!---
james2auto/james2auto is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
