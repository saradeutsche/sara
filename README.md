import React, { useState } from 'react';
import { Progress } from '@/components/ui/progress';
import { Button } from '@/components/ui/button';
import { Input } from '@/components/ui/input';

export default function CalorieCounter() {
    const [calories, setCalories] = useState(0);
    const [goal, setGoal] = useState(2000);
    const [input, setInput] = useState('');

    const handleAddCalories = () => {
        const newCalories = parseInt(input, 10);
        if (!isNaN(newCalories) && newCalories > 0) {
            setCalories(prev => prev + newCalories);
            setInput('');
        }
    };

    const handleReset = () => {
        setCalories(0);
    };

    return (
        <div className="flex flex-col items-center justify-center min-h-screen bg-gray-100 p-4">
            <div className="bg-white rounded-2xl shadow-xl p-6 w-full max-w-sm">
                <h1 className="text-2xl font-bold mb-4 text-center">Calorie Counter</h1>
                <p className="text-lg mb-2 text-center">Calories Today: <span className="font-semibold">{calories}</span></p>
                <Progress value={(calories / goal) * 100} className="mb-4" />
                <div className="flex gap-2 mb-4">
                    <Input 
                        type="number" 
                        value={input} 
                        onChange={(e) => setInput(e.target.value)} 
                        placeholder="Add calories" 
                        className="flex-1" 
                    />
                    <Button onClick={handleAddCalories}>Add</Button>
                </div>
                <Button onClick={handleReset} variant="secondary" className="w-full">Reset</Button>
            </div>
        </div>
    );
}
7890
